# Images

Images can be loaded into Mach::GL by creating a `MACH_IMAGE` object. 

```cpp
Graphics::MACH_IMAGE image = Graphics::Image::createImage("path.jpg", Graphics::ImageType::RGB);
```

When creating an image, the image type has to be defined. There are two types of images in Mach::GL: 

`Graphics::ImageType::RGB`  

`Graphics::ImageType::RGBA` 

By default, mipmapping is enabled when creating an image. However, to disable this create the image with the `createImage(...)` function varient: `Graphics::Image::createImage("path.jpg", Graphics::ImageType::RGBA, false)`. Where the third parameter is a boolean that toggles mipmapping. 

When createing a [Skybox](./../3D/skybox.md), a `Graphics::MACH_IMAGE` is required. However, a standard image will not work. For skyboxes, a cubemap image must be generated. This can be done by calling the constructor which takes in a list of 6 strings - this has to be a list of 6 or 12 strings. Any other number will cause a fail:  

```cpp
std::vector<std::string> filenames = {

    right.jpg,
    left.jpg,
    top.jpg,
    bottom.jpg,
    front.jpg,
    back.jpg
};

Graphics::MACH_IMAGE skyboxImage = Graphics::Image::createImage(filenames);
```