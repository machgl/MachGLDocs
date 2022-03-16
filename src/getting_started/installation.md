# Installation

## How to install: 

- For all platforms ensure you have git installed.

#### Windows (Support for VS 2019 only):

- Create a directory and navigate to it using: `cd path_to_directory`
- Run the command (INCLUDE the dot at the end) `git clone --recursive https://github.com/machgl/MachGL .`
- Within the working directory double-click on the windows_build_vs2019.bat file. This will make a VS solution file which can be opened
- Once VS is open, right click on the 'Sandbox' project and select 'Set Default Startup Project'
- Build the solution

#### MacOS (Support for XCode only):

- Create a directory and navigate to it using: `cd path_to_directory`
- Run the command (INCLUDE the dot at the end) `git clone --recursive https://github.com/machgl/MachGL .`
- Run the command `./macos_build_xcode.sh` to build the xcode workspace
- Open the generated XCode workspace file and navigate in the menu bar to Product -> Scheme and click on 'Sandbox' 
- Build the solution

##### Note (MacOS Only) 
Once the solution has been built, the 'CoreAssets' folder in MachGL must be copied into the build directory (To be fixed).


### Custom Projects 
Please see the Sandbox project for OpenGL and Vulkan Sandbox for Vulkan projects. These are good bases to start from, however, if you want to create your own project, please duplicate the premake5.lua script into your custom project folder and edit the premake5.lua script in the root directory to include this custom project. 

## Links

GitHub - [Click Here](https://github.com/machgl/MachGL)  
Website - [Click Here](https://mach-gl.com)  
E-Mail - james@mach-gl.com  