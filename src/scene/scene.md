# Scenes 

In Mach::GL, the best way to handle rendering objects and grouping these objects is with a scene. Scenes are created by creating a `MACH_SCENE` object - this object is located in the MachGL::Scene namespace. 

A scene takes in the parameters of a [Projection Matrix](./../utilities/maths.md) and a [Camera](./../objects/camera.md) object.

```cpp 
Scene::MACH_SCENE scene = Scene::Scene::createScene(projectionMatrix, camera);
```

Any objects that are to be rendered in the scene need to be pushed to the scene by the `scene->pushObject(object)` function. If there are many objects that share the same shader then it is recommended to use [Groups](./groups.md) instead to reduce the number of shader enable/disable functions to the graphics API.

[Groups](./groups.md) have to be pushed to the scene in a similar way as objects by calling the `group->pushObject(object)` function. However, objects that are in a group should not also be pushed to a scene separately. 

[Skyboxes](./../3D/skybox.md) can easily be added to a scene by calling the `scene->setSkybox(skybox)` function during the initialization of the scene. 