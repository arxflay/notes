OpenGL is an API but also a standard what function should be implemented and how they should behave. Khornos Group (Maintainer of OpenGL standard) doesn't provide implementation, instead GPU Vendors will have to make their own implementations

OpenGL have two modes, immediate and core profile. Immediate = easy but slow and limited API. Core profile = harder (requires understanding how graphics programming wokr) but faster and richer

OpenGL Context - Big state machine (Imagine as a class with many properties and function) where OpenGL stores objects and data. All commands works with that single context and because of that, rendering from multithreads is prohibited.

Instead of C constructs (structs, union) OpenGL relies on handles that act like objects (similar to WinAPI) and pointers to data - easy for porting to other languages. User can configure object and reuse it later without reconfiguration.  Here is pseudo code (not actual code). 
```
// hypotetical implementation

struct ColorData
{
	uint8_t r;
	uint8_t g;
	uint8_t b;
};

class GLContext
{
/*some fns*/
private:
	ColorData *m_data;
	/*other fields*/
};

// hypotetical client code

uint32_t handle = glGenObject(GL_COLOR_DATA);
glBindObject(handle, GL_COLOR_DATA);
uint8_t value = 128;
glSetData(GL_COLOR_DATA_COMPONENT_R, &value);
glBindObject(0, GL_COLOR_DATA); // m_data is null now
value = 0;
glGetData(GL_COLOR_DATA_COMPONENT_R, &value); // will return error
glBindObject(handle, GL_COLOR_DATA)
glGetData(GL_COLOR_DATA_COMPONENT_R, &value); // will return 128
```

OpenGL as API doesn't manage window, context creation. This is solved by OS native functions (for example windows CreateWindow and wglCreateContext, linux x11 XCreateSimpleWindow and glXCreateContext). There are libraries that simplify window and context management - GLFW, SDL, SFML raylib.

OpenGL functions must be retrieved manually because OS don't know upfront what version of OpenGL specification we want to use. Each function is retrieved by OS provided function, for example win wglGetProcAddr. Libraries like GLAD solve this problem, other libraries can do it when creating window

### GLFW

GLFW context will

Typical code consists:
1. Init glfw (glfwInit)
2. Setting version and profile hints (glfwWindowHint)
3. Create Window (glfwCreateWindow)
4. Set context (glfwMakeContextCurrent)
5. Load all functions (function are bound to context) gladLoadGLLoader
6. Set size of GL viewport (glViewPort), must be called on resize (by setting callback)
7. Create rendering loop (while true)
8. Poll events (glfwPollEvents)
9. Swap buffers (glfwSwapBuffers)
10. Cleanup (glfwTerminate)

buffer swapping - swapping between current buffer and buffer with image that was rendered. Without buffer swapping artifacts will be visible.

Normalized coordinate system - coordinate system that use values from -1 to 1. This system is used by OpenGL because screens/windows have different size and so normalized value can be easily transformed to screen coordinates.

glClear - clear buffers specifying bit (or sequence) of buffer we want to clear. Values: STENCIL_BUFFER_BIT, COLOR_BUFFER_BIT, DEPTH_BUFFER_BIT

glClearColor - set color that will be used when glClear with COLOR_BUFFER_BIT is called


### Drawing
Everything in OpenGL is 3D, OpenGL task is convert 3D data to 2D (monitors are not 3d obviously)
Vertex Data = Collection of vertices
Vertex = Collection of attributes per 3D coordinate

OpenGL graphics pipeline:
1. Vertex Stage (vertex shader) - outputs 3d coordinate from vertex data
2. Assembly Shape - assembles primitive from output of vertex stage
3. Geometry stage (geometry shader) - creates extra shapes from existing if user provided geometry shader
4. Rasterization - conversion of vector graphics to 2d fragments (in simple terms - unprocessed pixels). Fragments outside of range are discarded
5. Fragment Stage (fragment shader) - advanced effects and pre final output Fragment - everything needed to draw single pixel (data from shaders, data from rasterization stage)
6. Test Stage - pixel blending, stencils, depth testing. Final output
Each step of OpenGL graphic pipeline is separated and does one thing
Shaders - small programs that run on GPU. User must provide at least vertex and fragment shader

To tell what to do with vertices you must specify OpenGL primitive. List of primitives: Triangle, Line, Strip, Quad, Point

Normalized coordinates - OpenGL doesn't use pixels, instead it uses normalized coordinates to draw. Coordinates range from -1.0 to 1.0, and coordinate is outside this range, it will be clipped. During drawing this coordinates are mapped to view port size (screen space coordinates), this transformation is named **viewport transformation**. Top is 1.0, bottom is -1.0, left is -1.0, 

#### Commands

VBO = VERTEX BUFFER OBJECT (GL_ARRAY_BUFFER, array of attributes) - unspecified data that are passed to vertex shader

VAO = VERTEX ARRAY OBJECT - stores information about attributes, bound EBO, enabled attributes. Without it we had to specify VBO and attribute pointers manually for each drawing sequence

`glGenBuffer(count, bufferPtr)`- generate buffer with unspecified data
`glBindBuffer(type, bufferHandle`) - bind bufferHandle as buffer for type `type`. To unbind buffer, pass bufferHandle with 0. Bound buffer will be used for related operations with it. `type` - type of object we want to bind, for example GL_ARRAY_BUFFER (vertex attribute array)
`glBufferData(bufferType, buffer, length, storageType)` - Set buffer data for currently bound buffer of type bufferType. `storageType` is GPU hint where is the best place to put data

StorageTypes:
1. GL_STREAM_DRAW - data are read a few times and  changed only once 
2. GL_STATIC_DRAW - data are read often and changed only once 
3. GL_DYNAMIC_DRAW - data are changed and read  often

`glVertexAttribPointer(index, size, type, stride, normalize, offset` - This function is used to define attribute of vertex of type `type` that is located on `index`. `stride` is after how much bytes is next attribute found. Offset between indices is represented by `offset` ptr. `size` is amount of components of attribute, max is 4. `normalize` bool specifies if we want to data to be normalized
Positition of attribute is calculated via: $pos = offset + stride * i$
1. `offset` and `stride` is not required if each attribute is in different VBO. Data are tightly packed
```cpp
	glBindBuffer(GL_ARRAY_BUFFER, VBO[0]);
	glBufferData(GL_ARRAY_BUFFER, sizeof(vertices), vertices, GL_STATIC_DRAW);
	glVertexAttribPointer(0, 3, GL_FLOAT, GL_FALSE, sizeof(float) * 3, (void*)0);
	glEnableVertexAttribArray(0);
	
	glBindBuffer(GL_ARRAY_BUFFER, VBO[1]);
	glBufferData(GL_ARRAY_BUFFER, sizeof(color), color, GL_STATIC_DRAW);
	glVertexAttribPointer(1, 3, GL_FLOAT, GL_FALSE, sizeof(float) * 3, (void*)0);
	glEnableVertexAttribArray(1);
```
2. if attributes are sequentially batched VBO (aaaa, xxxx) then offset must be specified. Data are tightly packed
3. if attributes are interleaved, e.g after another (axaxaxaxax) then `stride` and `offset` must be specified. Data are not tightly packed
`glVertexAttribPointer` can point to different VBO

`glEnableVertexAttribArray` - enable attribute (by default attributes are disabled)

`glCreateShader(type)` - create shader of type `type`
shader types:
1. GL_VERTEX_SHADER
2. GL_FRAGMENT_SHADER
3. GL_GEOMETRY_SHADER
`glDeleteShader(handle)` - deletes shader
`glGetShaderiv` - get shader int property GL_COMPILE_STASUS - shader compile status property
`glCompileShader` - compile shader
`glShaderInfoLog` - get shader info log

`glCreateProgram()` - create shader program
`glAttachShader(shaderProgramHandle, shaderHandle)` - attach shader
`glUseProgram()` - bind shader program
`glGetProgramiv` - get program in property GL_LINK_STATUS - shader program link status
`glProgramInfoLog` - get program info log
`glGetError` - get error code

Simple vertex shader:
```glsl
#version 330 core
layout (location = 0) in vec3 aPos;
void main()
{
	gl_Position = vec4(aPos.x, aPos.y, aPos.z, 1.0);
}
```
Each shader must contain `#version` with specified version and profile, in this example 3.3 with core profile
layout (location = 0) - index of vertex attribute. Glsl will map this location to what we set in `glVertexAttribPointer` for specific index. layout is not required if in variables are sequenced exactly as set attributes in glVertexAttribPointer. Specifier attributes (like layout) must be before in/out/uniform keyword

fragment shader must have one out variable of vec4 which is a pixel color
```glsl
#version 330 core
out vec4 FragColor;
void main()
{
	FragColor = vec4(1.0f, 0.0f, 1.0f, 1.0f);
}
```


`glDrawArrays` - drawing function that draws vertex arrays

### Textures

Texture - nD image that wraps (n+1)D object. Texture could be 1d, 2d or even 3d (skybox). Wrapping 2d image around 3d object is named UV mapping

Texture coordinates - coordinates from range 0.0 to 1.0, from bottom-left to top-right. where 0.5 is center. Most image loaders however store image from top-left, so flipping Y will be required. Texture components conventionally namepd are stpq (s = x, t = y) or uv (u = x, v = y)

texel - texture pixel. final texture color is not exactly one to one mapping to pixels, it's mapping of floating value to image pixel value.

texture filtering - strategy how to determine color of pixel (texel).
Strategies provided by OpenGL
1. Nearest neighbor - picks nearest pixel that is pointed by floating point value. Results in visible pixels (GL_NEAREST_NEIGHBOR)
2. Linear filtering - linear interpolation between nearest pixels. Results in blurry image (GL_LINEAR)

texture wrapping - what to do if texture coordinates are bigger than 1.0.
GL_REPEAT - repeats pattern (wallpaper)
GL_MIRROR_REPEAT - repeats always mirrors pattern
GL_CLAMP_TO_EDGE - draw image from 0.0 to 1.0, outside parts repeats the edge of object (imagine as image in center and around it edge is repeated to the end of image)
GL_CLAMP_TO_BORDER - same as GL_CLAM_TO_EDGE, but we can specify color (via glClampColor) and this color will fill space outside of texture coordinates
