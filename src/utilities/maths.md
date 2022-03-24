# Maths

Mach::GL includes the entire glm maths library. However some types and functions have been renamed/simplified. 

## Renamed Types

`float2 = glm::vec2`  

`float3 = glm::vec3`  

`float4 = glm::vec4`  

`matrix4x4 = glm::mat4`  

These renamed types have access to all glm functions, operator overrides and can be used interchangably with the glm type names. 

## Projection Matrices 

There are 2 different projection matrices that have been implemented from glm specifically for Mach::GL, perspective and orthographic. Both have a normal and simplified version available. 

`Maths::perspective(fov, windowDimension, near, far);`  

`Maths::simplePerspective(fov, windowDimension);`   

`Maths::orthographic(left, right, top, bottom, near, far);` 

`Maths::simpleOrthographic(windowDimension);`  

Please note that these functions take in a WindowDimension object which can be retrieved from a [Window](./../getting_started/window.md) object.