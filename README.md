# cpp-project
cpp template project for cmake



# running and developing on windows with MSYS2

1. install MSYS2 compiler in c:/MSYS2
    - https://www.msys2.org/
2. run a NEW msys2 shell after completion
```
pacman -Syu
pacman -Sy git pkg-config mingw-w64-x86_64-make mingw-w64-x86_64-cmake mingw-w64-x86_64-gcc mingw-w64-x86_64-clang
```
3. close terminals and add C:\MSYS2\mingw64\bin to path of system variables
4. clone, build and run
```
cd ~/
git clone https://github.com/krebsalad/cpp-project.git
cd cpp-project/build
cmake ../ -G "MinGW Makefiles"
mingw32-make
```

# running and developing on ubuntu
1. start a terminal
```
sudo apt update -y
sudo apt upgrade -y
sudo apt install gcc g++ make cmake build-essential pkg-config git clang -y
```
3. clone, build and run
```
cd ~/
git clone https://github.com/krebsalad/cpp-project.git
cd cpp-project/build
cmake ../
make
```

# developing on vscode
1. install extensions C/C++, C++ Intellisense, Clang-Tidy, Clang-Format, CMake, CMake Tools,
2. (windows only, not required for linux) right click on the CMake Tools extension, then left click on the extension settings. Search for "generator". Under preffered generator left click on "edit in settings.json". In the file between "cmake.preferredGenerators": [  ], add the following  "MinGW Makefiles" in case of windows.
3. on the bottom click on "unspecified kit" then choose GNU 10.1.0
4. now press the play button to compile target 'run'
5. to enable clang-format add file .vscode/settings.json in directory TheNamelessEngine/ if not yet existing
6. in the file add between the {__} make sure "editor.formatOnSave": true and "clang-tidy.lintOnSave": true are set