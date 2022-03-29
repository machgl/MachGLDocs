# Objects

In Mach::GL, 3D models are stored in a `Object::MACH_OBJECT` object type. This type has multiple constructors: 

```cpp
    Object::MACH_OBJECT object = Object::Object::createObject(model, position, texture);

    Object::MACH_OBJECT object = Object::Object::createObject(model, position, texture, objectType);

    Object::MACH_OBJECT object = Object::Object::createObject(model, position, texture, texture2, objectType);
```

All three constructors take in a `Object::MACH_MODEL`, `float3` and `Graphics::MACH_IMAGE`. See [Model](./model.md) for more information on how to create an `Object::MACH_MODEL`. Two of these contructors take in an `Object::ObjectType` object which is an enum conistsing of three options:

```cpp
ObjectType::MESH

ObjectType::TERRAIN

ObjectType::SKYBOX
```

Please note that `ObjectType::SKYBOX` is usually reserved for internal engine use, however, is left available for custom skybox objects in which the built-in [Skybox](./skybox.md) is not suitable. 

The `ObjectType::TERRAIN` object type is mainly reserved for use with the built in Object::Terrain model generation. The only effect this currently has is to make the object not included in the render distance calculations in the renderer, see [Renderer3D](./../graphics/renderer3D.md). 

The constructor does not acutally load the object into memory/buffers, to do this the `object->create(objectProperties)` function has to be called and before this object is pushed to a scene, group or renderer. This function takes in an `Object::ObjectProperties` type and allows the developer to set the following properties: 

```cpp
Object::ObjectProperties objectProperties;

objectProperties.shineDamper = 1.0f;
objectProperties.reflectivity = 0.0f;
objectProperties.textureScale = 1.0f;
objectProperties.scale = float3(1);
objectProperties.color = float4(1);
```

The values above are the preset values and if these values are wanted then there is no need to re-set them in the code. If all values wanted are default, then there is no need to pass in the `Object::ObjectProperties` into the create function, and just `object->create()` can be called. 