# Building Jukebox for GD 2.2091 + Geode 6.0.0-alpha.1 (Windows)

Prerequisites: Visual Studio 2022 Build Tools (C++ workload + Windows SDK), CMake >= 3.21, Ninja,
Git, and Geode CLI >= 4.0.0 (`geode --version`).

```powershell
geode sdk install            # or clone https://github.com/geode-sdk/geode
cd <geode sdk dir>; git fetch --tags; git checkout v6.0.0-alpha.1
setx GEODE_SDK <geode sdk dir>   # reopen the terminal
geode sdk install-binaries       # Windows loader binaries for 6.0.0-alpha.1

cd jukebox-main
cmake -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
cmake --build build
# Output: build\fleym.nongd.geode
```
Or run the "Build Jukebox (Windows, Geode 6.0.0-alpha.1)" GitHub Actions workflow
(`.github/workflows/build-windows.yml`) and download the `jukebox-windows` artifact.
