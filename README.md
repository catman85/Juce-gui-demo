# Linux Setup for JUCE framework

## Features
- code-oss support
- C++ IntelliSense
- debugging
- .vscode automations

## Linux guide for creating projects like this
### Juce and Projucer 
1. Downkoad the JUCE framework and Projucer from https://juce.com/download/
1. Move the JUCE folder to your home directory ~
1. Execure the Projucer executable located in ~/JUCE/Projucer
1. File > Sign In > select enable gpl mode
1. Make sure the File > Global Paths are ok. (They should point to your ~/JUCE/ directory). Check for 
    1. Path to JUCE 
    2. JUCE modules
1. Create a new project from Projucer, give it a name, make sure the Linux-Makefile is checked, in the Exporters section

### Manual build
1. Go to your project foler and `Builds/LinuxMakeFile`. Run `make CONFIG=Debug` to make sure you can build the file, and not missing any dependencies.
1. Execute the executable located in `Builds/LinuxMakefile/build/DemoApp` or check that your vst is created, depending on the options you set in Projucer

### Code-Oss
1. Install the C/C++ IntelliSense extension for code-oss
1. `sudo pacman -S gdb` for the debugger to work

### `c_cpp_properties.json`
1. update the usr/include/c++/x.x.x versions to match the ones installed in your system
1. update the usr/lib/gcc/ versions to match the ones installted in your system
1. Make sure the JUCE and JUCE/modules paths are correct

### `launch.json`
1. make sure the `linux.program` path specified, matches the one that occurs by manually building the app with the make command

### Running the app
1. Click `ctrl+shift+b` to open the tasks menu in vscode
    1. clean all
    1. build
1. Go to the run menu in the left side menu and select C++ Launch (The debugger should work by putting a breakpoint in vscode editor)

## Resources
- https://www.reddit.com/r/JUCE/comments/bbrjsb/how_to_run_juce_project_on_linux/
- https://stackoverflow.com/questions/46258143/visual-studio-code-how-to-configure-includepath-for-better-intellisense-results
- https://github.com/icq4ever/emptyJUCEProject
- https://github.com/ChristopherJohnston/HelloWorldPlugin

