# Computer graphics in Game development course

This repo contains a template for Computer graphics in Game development labs

## Pre-requirements

- Version control: [Git](https://git-scm.com/)
- Build automation: [CMake](https://cmake.org/download/)
- C++ compiler: MSVC on Windows, Clang on MacOS, GCC on Linux (C++17 compatible)
- [OpenMP library](https://www.openmp.org/)
- Source code editor: [Visual Studio Code](https://code.visualstudio.com/Download)

For DirectX12 you need a Windows machine or VM with installed software and [Windows SDK](https://developer.microsoft.com/en-us/windows/downloads/windows-sdk/).
For graphics debugging you may to install [Microsoft PIX](https://devblogs.microsoft.com/pix/download/).

## How to build the solution

Use `git clone --recursive` to clone the repo with submodules or run `git submodule update --init --recursive` after the first clone.

Go to the project folder and run the next command:

```sh
mkdir Build
cd Build
cmake ..
```

## Third-party tools and data

- [STB](https://github.com/nothings/stb) by Sean Barrett (Public Domain)
- [Linalg.h](https://github.com/sgorsten/linalg) by Sterling Orsten (The Unlicense)
- [Tinyobjloader](https://github.com/syoyo/tinyobjloader) by Syoyo Fujita (MIT License)
- [Cxxopts](https://github.com/jarro2783/cxxopts) by jarro2783 (MIT License)
- [Cornell Box models](https://casual-effects.com/g3d/data10/index.html#) by Morgan McGuire (CC BY 3.0 License)
- [Cube model](https://casual-effects.com/g3d/data10/index.html#) by Morgan McGuire (CC BY 3.0 License)
- [Teapot model](https://casual-effects.com/g3d/data10/common/model/teapot/teapot.zip) by Martin Newell (CC0 License)
- [Dabrovic Sponza model](https://casual-effects.com/g3d/data10/index.html#) by Marko Dabrovic (CC BY-NC License)

# Creative Task Description for Rasterization

### Files Modified and Their Purpose

- **rasterizer_renderer.cpp**: The `apply_sepia_tone_filter` method called for the sepia tone filter effect.
- **rasterizer.h**: Added the `apply_sepia_tone_filter` method, which applies a sepia filter to the rendered image by iterating over pixels and converting them using the sepia formula.

The task implements rasterization, applying a sepia tone filter to the final render output, transforming pixel colors to create a classic visual effect.

- Before:
  ![image](https://github.com/user-attachments/assets/9f455c42-38c1-4c66-b52a-03344bc325bb)

- After:
  ![image](https://github.com/user-attachments/assets/0784ea17-e3e7-485d-bb88-463a2ddf440b)

# Creative Task Description for Raytracing

### Files Modified and Their Purpose

The task implements raytracing, adjusting `closest_hit_shader` for Monte-Carlo light tracing.

- result.png:
  ![result](https://github.com/user-attachments/assets/a171893c-976c-4d51-b36d-e4a5d6d1794e)

- raytracing_depth(3), accumulation_num(16):
  ![creative_task_3-16](https://github.com/user-attachments/assets/01efd38c-3e48-47df-b64c-7f4016c226d6)

- raytracing_depth(3), accumulation_num(128):
  ![creative_task_3-128](https://github.com/user-attachments/assets/c944c089-8751-4ade-b0df-64e328d314c8)  


# Task Description for DX12

### Files Modified, Their Purpose And Some Results

cube.obj:
![image](https://github.com/user-attachments/assets/cb6b1bd9-39fe-47fc-8ed2-6072c68524f5)

z-test.obj:
![image](https://github.com/user-attachments/assets/be5b2bfc-7d3e-4b01-b206-d138465ed41b)

launch.json:
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "(Windows) Launch",
            "type": "cppvsdbg",
            "request": "launch",
            "program": "${workspaceFolder}/build/Debug/DirectX12.exe",
            "args": ["--model_path", "models/CornellBox-Sphere.obj"],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "console": "externalTerminal"
        }


    ]
}
```
