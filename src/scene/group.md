# Groups

Groups are a container for multiple objects that all share the same shader. 

```cpp 
Scene::MACH_GROUP group = Scene::Group::createGroup(shader, projectionMatrix);
```

To be able to render objects, they have to be pushed into the group using the function `group->pushObject(object)`.

All groups have to be pushed to scenes (see [Scenes](./scene.md)) to be able to render the objects in the group. 