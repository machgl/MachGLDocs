# Images

Images can be loaded into Mach::GL by creating a `MACH_IMAGE` object. 

```cpp
Graphics::MACH_IMAGE image = Graphics::Image::createImage("path.jpg", Graphics::ImageType::RGB);
```

When creating an image, the image type has to be defined. There are two types of images in Mach::GL: 

`Graphics::ImageType::RGB`  

`Graphics::ImageType::RGBA` 

By default, mipmapping is enabled when creating an image. However, to disable this create the image with the `createImage(...)` function varient: `Graphics::Image::createImage("path.jpg", Graphics::ImageType::RGBA, false)`. Where the third parameter is a boolean that toggles mipmapping. 