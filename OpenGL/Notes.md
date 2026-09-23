OpenGL is an API but also a standard specifying what functions should be implemented and how they should behave. The Khronos Group (maintainer of the OpenGL standard) doesn't provide an implementation; instead, GPU vendors have to make their own implementations

OpenGL has two modes, immediate and core profile. Immediate = easy but slow and limited API. Core profile = harder (requires understanding how graphics programming works) but faster and richer

OpenGL Context - A big state machine (imagine it as a class with many properties and functions) where OpenGL stores objects and data. All commands work with that single context, and because of that, rendering from multiple threads is prohibited.

Instead of C constructs (structs, unions), OpenGL relies on handles that act like objects (similar to WinAPI) and pointers to data - easy to port to other languages. The user can configure an object and reuse it later without reconfiguration.  Here is pseudocode (not actual code). 
```
// hypothetical implementation

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

// hypothetical client code

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

OpenGL as an API doesn't manage window or context creation. This is handled by native OS functions (for example, Windows CreateWindow and wglCreateContext, and Linux X11 XCreateSimpleWindow and glXCreateContext). There are libraries that simplify window and context management - GLFW, SDL, SFML, and raylib.

OpenGL functions must be retrieved manually because the OS doesn't know upfront what version of the OpenGL specification we want to use. Each function is retrieved by an OS-provided function, for example, Windows wglGetProcAddr. Libraries like GLAD solve this problem; other libraries can do it when creating a window

### GLFW

GLFW context will

Typical code consists of:
1. Initializing GLFW (glfwInit)
2. Setting version and profile hints (glfwWindowHint)
3. Creating a window (glfwCreateWindow)
4. Setting the context (glfwMakeContextCurrent)
5. Loading all functions (functions are bound to the context) gladLoadGLLoader
6. Setting the size of the GL viewport (glViewPort), which must be called on resize (by setting a callback)
7. Creating a rendering loop (while true)
8. Polling events (glfwPollEvents)
9. Swapping buffers (glfwSwapBuffers)
10. Cleaning up (glfwTerminate)

buffer swapping - swapping between the current buffer and the buffer with the image that was rendered. Without buffer swapping, artifacts will be visible.

Normalized coordinate system - a coordinate system that uses values from -1 to 1. This system is used by OpenGL because screens/windows have different sizes, and so a normalized value can be easily transformed into screen coordinates.

glClear - clears buffers by specifying the bit (or sequence) of the buffer we want to clear. Values: STENCIL_BUFFER_BIT, COLOR_BUFFER_BIT, DEPTH_BUFFER_BIT

glClearColor - sets the color that will be used when glClear with COLOR_BUFFER_BIT is called


### Drawing
Everything in OpenGL is 3D; OpenGL's task is to convert 3D data to 2D (monitors are not 3D, obviously)
Vertex Data = Collection of vertices
Vertex = Collection of attributes per 3D coordinate

OpenGL graphics pipeline:
1. Vertex Stage (vertex shader) - outputs a 3D coordinate from vertex data
2. Assembly Shape - assembles a primitive from the output of the vertex stage
3. Geometry stage (geometry shader) - creates extra shapes from existing ones if the user provided a geometry shader
4. Rasterization - conversion of vector graphics to 2D fragments (in simple terms - unprocessed pixels). Fragments outside the range are discarded
5. Fragment Stage (fragment shader) - advanced effects and pre-final output. Fragment - everything needed to draw a single pixel (data from shaders, data from the rasterization stage)
6. Test Stage - pixel blending, stencils, depth testing. Final output
Each step of the OpenGL graphics pipeline is separate and does one thing
Shaders - small programs that run on GPU. User must provide at least vertex and fragment shader

To specify what to do with vertices, you must specify an OpenGL primitive. List of primitives: Triangle, Line, Strip, Quad, Point

Normalized coordinates - OpenGL doesn't use pixels; instead, it uses normalized coordinates to draw. Coordinates range from -1.0 to 1.0, and if a coordinate is outside this range, it will be clipped. During drawing, these coordinates are mapped to the viewport size (screen space coordinates); this transformation is named **viewport transformation**. The top is 1.0, the bottom is -1.0, and the left is -1.0, 

#### Commands

VBO = VERTEX BUFFER OBJECT (GL_ARRAY_BUFFER, array of attributes) - unspecified data that is passed to the vertex shader

VAO = VERTEX ARRAY OBJECT - stores information about attributes, the bound EBO, and enabled attributes. Without it, we would have to specify VBO and attribute pointers manually for each drawing sequence. Also stores the EBO

`glGenBuffer(count, bufferPtr)`- generates a buffer with unspecified data
`glBindBuffer(type, bufferHandle`) - bind bufferHandle as buffer for type `type`. To unbind buffer, pass bufferHandle with 0. Bound buffer will be used for related operations with it. `type` - type of object we want to bind, for example GL_ARRAY_BUFFER (vertex attribute array)
`glBufferData(bufferType, buffer, length, storageType)` - Sets buffer data for the currently bound buffer of type bufferType. `storageType` is a GPU hint indicating the best place to put the data

StorageTypes:
1. GL_STREAM_DRAW - data is read a few times and changed only once 
2. GL_STATIC_DRAW - data is read often and changed only once 
3. GL_DYNAMIC_DRAW - data is changed and read often

`glVertexAttribPointer(index, size, type, stride, normalize, offset` - This function is used to define an attribute of a vertex of type `type` that is located at `index`. `stride` is the number of bytes after which the next attribute is found. The offset between indices is represented by the `offset` ptr. `size` is the number of components of the attribute; the maximum is 4. The `normalize` bool specifies if we want the data to be normalized
The position of the attribute is calculated via: $pos = offset + stride * i$
1. `offset` and `stride` are not required if each attribute is in a different VBO. Data is tightly packed
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
2. if attributes are sequentially batched in a VBO (aaaa, xxxx), then the offset must be specified. Data is tightly packed
3. if attributes are interleaved, e.g., one after another (axaxaxaxax), then `stride` and `offset` must be specified. Data is not tightly packed
`glVertexAttribPointer` can point to different VBO

`glEnableVertexAttribArray` - enables an attribute (by default, attributes are disabled)

`glCreateShader(type)` - creates a shader of type `type`
shader types:
1. GL_VERTEX_SHADER
2. GL_FRAGMENT_SHADER
3. GL_GEOMETRY_SHADER
`glDeleteShader(handle)` - deletes a shader
`glGetShaderiv` - gets the shader int property GL_COMPILE_STASUS - shader compile status property
`glCompileShader` - compiles a shader
`glShaderInfoLog` - gets the shader info log

`glCreateProgram()` - creates a shader program
`glAttachShader(shaderProgramHandle, shaderHandle)` - attaches a shader
`glUseProgram()` - binds a shader program
`glGetProgramiv` - gets the program int property GL_LINK_STATUS - shader program link status
`glProgramInfoLog` - gets the program info log
`glGetError` - gets an error code

Simple vertex shader:
```glsl
#version 330 core
layout (location = 0) in vec3 aPos;
void main()
{
	gl_Position = vec4(aPos.x, aPos.y, aPos.z, 1.0);
}
```
Each shader must contain `#version` with a specified version and profile, in this example, 3.3 with the core profile
layout (location = 0) - the index of the vertex attribute. GLSL will map this location to what we set in `glVertexAttribPointer` for a specific index. layout is not required if in variables are sequenced exactly as the attributes set in glVertexAttribPointer. Specifier attributes (like layout) must be before the in/out/uniform keyword

A fragment shader must have one out variable of vec4, which is a pixel color
```glsl
#version 330 core
out vec4 FragColor;
void main()
{
	FragColor = vec4(1.0f, 0.0f, 1.0f, 1.0f);
}
```


`glDrawArrays` - a drawing function that draws vertex arrays

uniform - an object that is accessible in all shaders (global) in a single shader program. To write a value to a uniform, you must retrieve the location of the named uniform (which is unique per shader program) in the shader program via `glGetUniformLocation` and then set the value via `glUniformX` functions. Before setting the value, you must bind the shader program.

EBO (GL_ELEMENT_ARRAY_BUFFER) - an element object buffer that contains indices of vertices that have to be drawn (to reduce the amount of vertex data). For example, we can draw a triangle from 6 vertices, or we can use 4 vertices and specify 6 indices.
`glDrawElements` - an alternative drawing function that uses an EBO.

`glPolygonMode(face, mode)` - determines how to draw polygons (objects that form a closed polygonal chain, for example, a triangle). `face` determines which polygons, front or/and back, the mode should be applied to. The `face` value `GL_FRONT_AND_BACK` applies to both the back and front modes
modes:
1. GL_FILL - default, fills closed space
2. GL_LINE - draws only lines (wireframe)
3. GL_POINT - draws only dots


### Textures

Texture - an nD image that wraps an (n+1)D object. A texture could be 1D, 2D, or even 3D. Wrapping a 2D image around a 3D object is called UV mapping

Texture coordinates - coordinates ranging from 0.0 to 1.0, from bottom-left to top-right, where 0.5 is the center. Most image loaders, however, store images from the top-left, so flipping Y will be required. Texture components are conventionally named stpq (s = x, t = y) or uv (u = x, v = y)

texel - a texture pixel. The final texture color is not exactly a one-to-one mapping to pixels; it's a mapping of a floating value to an image pixel value. `texture sampling` - retrieving a color from a texture using coordinates

texture filtering - a strategy for determining the color of a pixel (texel).
Strategies provided by OpenGL
1. Nearest neighbor - picks the nearest pixel that is pointed to by a floating-point value. Results in visible pixels (GL_NEAREST)
2. Linear filtering - linear interpolation between the nearest pixels. Results in a blurry image (GL_LINEAR)

Filters can be set for:
1. Magnifying (GL_TEXTURE_MAG_FILTER) - when image is upscaled
2. Min (GL_TEXTURE_MIN_FILTER) - when image is downscaled

texture wrapping - what to do if texture coordinates are bigger than 1.0.
GL_REPEAT - repeats pattern (wallpaper)
GL_MIRROR_REPEAT - repeats and always mirrors the pattern
GL_CLAMP_TO_EDGE - draws the image from 0.0 to 1.0; the outside parts repeat the edge of the object (imagine an image in the center, and around it, the edge is repeated to the end of the image)
GL_CLAMP_TO_BORDER - the same as GL_CLAM_TO_EDGE, but we can specify a color (via glClampColor), and this color will fill the space outside the texture coordinates

`glGenTextures` - generates an unspecified texture
`glBindTexture` - similar to glBindBuffer, but TEXTURE_nD constants are passed

mipmaps - a sequence of images that are smaller than the texture. Mipmaps are used to let OpenGL easily determine the pixel color of a distant object. OpenGL can generate mipmaps for us using the function `glGenMipmaps`. 

Additional texture filters are available when a mipmap is enabled in the form `GL_<FILTER>_MIMAP_<FILTER2>` where FILTER and FILTER2 are one of the two filters

`glTexImage2D(target, level, internal_format, width, height, border, format, type, data` - sets a 2D texture for the target (2D_TEXTURE or CUBE_MAP). `level` is the mipmap level (if we want to generate mipmaps manually); 0 is the default level. `internal_format` is the format of the data. `border` is a legacy parameter that should always be 0. `type` is the length of a single data element (GL_UNSIGNED_BYTE = 0 bytes)

Texture unit (TMU) - the part of the GPU responsible for storing textures and performing operations on them

To activate a specific texture unit, the function `glActivateUnit(unitN)` is used, where unitN is the unit we want to use (from 0 to 15). After activation, the currently bound texture will be reset to the last used texture. Generally, you have to call `glActivateUnit` and then `BindTexture` 

You can specify which texture unit must be used for a sampler via `glUniformiv`

typical texture flow
```
glActivateUnit - activate unit
glGenTextures - get unspecified texture
glBindTexture - bind TEXTURE_2D
glTexImage2D - set texture data
glUniformiv - to set what texture unit must be used by sampler2D
```

### Texture - shader

texture sampler (GLSL type `samplerND`) - a texture stored in a texture unit
`texture(sampler, textureCoordinates)` - glsl function that retrieves texture pixel color
`mix(a, b, percentage)` - linear interpolation between two vectors

example fragment shader
```glsl
#version 330 core
uniform sampler2D texture0;
in vec2 texPos;
out vec4 FragColor;
void main()
{
	FragColor = texture(texture0, texPos);
}
```
