# Skybox

A skybox can be created by using a `MACH_SKYBOX` object, the `createSkybox()` function takes in a `MACH_IMAGE` (see [Image](./../graphics/image.md)).

```cpp 
Object::MACH_SKYBOX skybox = Object::Skybox::createSkybox(skyboxTexture);
```

To render the skybox, the `skybox->render(projectionMatrix, cameraViewMatrix)` function needs to be called. 

The skybox object should be rendered last, however if the skybox is included in a scene, then the `render(...)` function does not have to be called. 

