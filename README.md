[![License: MIT](https://img.shields.io/packagist/l/doctrine/orm.svg)](https://opensource.org/licenses/MIT)

# SDF Baking
An OpenGL sample that demonstrates baking Signed Distance Fields (SDF) into 3D textures using compute shaders and using them to add Soft Shadows and Ambient Occlusion to a rasterized scene.

## Screenshots
![SDFBaking](data/screenshot_1.jpg)
![SDFBaking](data/screenshot_2.jpg)

## Building

### Windows
Tested on: Windows 10 version 21H1

Prerequisites
* MSVC 19.00 or higher
* CMake 3.8 or higher

```
git clone --recursive https://github.com/diharaw/SDFBaking.git
cd SDFBaking
mkdir build
cd build
cmake -G "Visual Studio 16 2019" ..
```

## Dependencies
* [dwSampleFramework](https://github.com/diharaw/dwSampleFramework) 

## License
```
Copyright (c) 2021 Dihara Wijetunga

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and 
associated documentation files (the "Software"), to deal in the Software without restriction, 
including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial
portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT 
LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. 
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE 
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
