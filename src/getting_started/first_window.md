# First Window

## Create the Window


Include the Mach::GL header and set the namespace to MachGL (using MachGL namespace not necessary, but a convenience) N.B. All functions and objects related to Mach::GL are under the MachGL namespace.

```cpp
#include "../MachGL/MachGL.h"

using namespace MachGL;
```

In the "main" function of your program, create an object of `MACH_WINDOW`. This is a shared pointer to a "Window" object and is API abstracted. Currently, only GLFW is supported, but the window created will be dependant on operating system and chosen graphics API in the future. Any window properties like `MSAA(x)`, ` disableCursor()` or ` fullscreen()` have to be called before the `init()` function.    

```cpp
MACH_WINDOW window = Window::createWindow("Window Title", width, height);
window->MSAA(4);
window->init();
```

The main game loop should be defined in the "main" function of the program. This can be created by checking if the window is not closed using the `window->closed()` function. This loop should contain any functions that need to be updated every frame. For example, `window->clear()` to clear the screen and `window->update()` to swap the framebuffers (ie. render any changes from the within the function to the screen). 

```cpp
while(!window->closed()) {

    window->clear();
    window->update();
}
```

When the main game loop has exited, the window should be destroyed and closed using the `window->close()` function

### Example code:

```cpp
#include "../MachGL/MachGL.h"

using namespace MachGL;

int main() {

    uint32_t width = 1920;
    uint32_t height = 1080;

    //Create window, define MSAA settings (4x) and initilize window
    MACH_WINDOW window = Window::createWindow("Window Title", width, height);
    window->MSAA(4);
    window->init();

    //Start game loop which will run until window is closed
    while (!window->closed()) {

        //Clear the window
        window->clear();

        //Swap the framebuffers
        window->update();
    }

    //Close and destroy the window
    window->close();
    
    //End of program
    return 0;
}
```