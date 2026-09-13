## Zsh
`>` redirect stdout to file
`fd>` redirect fd to file, creating or truncating a new file
`fd>> or >>` redirect output to file, appending to existing file
`<` redirect file to stdin
`|` pipe output to another process, example `glxinfo -B | grep OpenGL`

## Sed

Chaining command by using `;` in script or multiple `-e`