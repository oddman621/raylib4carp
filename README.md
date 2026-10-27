# raylib4carp
 Raylib Binding for personal use

# Current Status
Usable... I think?

## Caution
Functionality of all features is not guaranteed!

# Notice
* Carp version is 0.6.0, Raylib version is 6.2.
* Implementation:
  - [x] raylib.h
  - [ ] rlgl.h
  - [ ] raymath.h
* `prn` warning: I don't know how to fix it.
* `CChar`: I don't know what is this.
* Struct with Fixed-length array is opaque.
* `typedef A *B;`: No type alias support in Carp. `(typedef A (Ptr B))` doesn't work, for example. Following type is not available now. Use the right side instead, if you have a problem:
  - `Quaternion`: `Vector4`
  - `Texture2D`: `Texture`
  - `TextureCubemap`: `Texture`
  - `Camera`: `Camera3D`
  - `ModelAnimPose`: `(Ptr Transform)`
