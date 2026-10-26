# raylib4carp
 Raylib Binding for personal use

# Notice
* Carp version is 0.6.0, Raylib version is 6.2.
* Implementation:
  - [x] raylib.h
  - [ ] rlgl.h
  - [ ] raymath.h
* `prn` warning: I don't know how to fix it.
* `CChar`: I don't know what is this.
* Fixed-length array is defined to `(Ptr t)` with length comment.
* `typedef A *B;`: No type alias support in Carp. `(typedef A (Ptr B))` doesn't work, for example. Following type is not available now. Use the right side instead:
  - `Quaternion`: `Vector4`
  - `Texture2D`: `Texture`
  - `TextureCubemap`: `Texture`
  - `Camera`: `Camera3D`
  - `ModelAnimPose`: `(Ptr Transform)`
* Missing functions identified so far:
  - [ ] IsWindowState
  - [ ] SetWindowState
  - [ ] ClearWindowState
  - [ ] GetMonitorName
  - [ ] GetClipboardText
  - [ ] SetRandomSeed
  - [ ] LoadRandomSequence
  - [ ] LoadFileData
  - [ ] UnloadFileData
  - [ ] ExportDataAsCode
  - [ ] UnloadFileText