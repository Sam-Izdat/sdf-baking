# Compiling with VS 2022 on Windows 10

## Prerequisites

Visual Studio 17 2022 needs to be told to install CMake support and Windows 10 SDK. Under "Tools" -> "Get Tools and Features" make sure "Desktop development with C++" is installed. Then tick:

- "C++ CMake tools for Windows"
- "Windows 10 SDK [...]"

WIN32 is not defined for some reason and required for dependencies. Can add to `CMakeLists.txt`:

    add_definitions(-DWIN32) 

May need to install zlib with vcpkg.

Build with:

    cmake -DCMAKE_CXX_FLAGS="/EHsc" -G "Visual Studio 17 2022" ..

Load solution. Right-click "SDFBaking" and "Set as Startup Project" then compile with debugger.

## Errors to fix

In `main.cpp`, problems caused by line:

    m_bake_sdf_program->set_uniform("u_VolumeSize", volume_size);

There's an undefined overload in `dwSampleFramework` for `set_uniform` with `ivec3` -- declare in `ogl.h`:

    bool    set_uniform(std::string name, glm::ivec3 value);

...and define in `olg.cpp`:

    bool Program::set_uniform(std::string name, glm::ivec3 value)
    {
        if (m_location_map.find(name) == m_location_map.end())
            return false;

        glUniform3i(m_location_map[name], value.x, value.y, value.z);

        return true;
    }

Does not seem to be VS version related, but what do I know.
