# raylib4carp
 Raylib Binding for Carp language  
  
It's a personal project, but feel free to use it.
 
Requires raylib to be installed on the system.

**Caution: Functionality of all features is not guaranteed!**


# Notice
* Carp version is 0.6.0, Raylib version is 6.2.
* Implementation:
  - [x] raylib.h
  - [ ] rlgl.h
  - [ ] raymath.h
* Tested on Linux x86_64. Other platforms are not tested.
* Focused on implementation over convenience... for now.

## Issues
* No fixed array in Carp: Struct with Fixed-length array is opaque.
* `prn` warning: I don't know how to fix it.
* `CChar`: I don't know what is this.
* No type alias support in Carp. `(typedef A (Ptr B))` doesn't work, for example. Following type is not available now. Use the right side instead, if you have a problem:
  - `Quaternion`: `Vector4`
  - `Texture2D`: `Texture`
  - `TextureCubemap`: `Texture`
  - `Camera`: `Camera3D`
  - `ModelAnimPose`: `(Ptr Transform)`

## TODOs
* Exposed functions should be practical, not just "Implementation done.".

# Example

```
(load "https://github.com/oddman621/raylib4carp@main")

(defn-do main []
  (init-window 800 450 (cstr "Carp Raylib Test"))
  (set-target-fps 60)
  (while-do (not (window-should-close))
    (begin-drawing)
    (clear-background Color.raywhite)
    (draw-text (cstr "Congrats! You created your first window!") 100 200 20 Color.lightgray)
    (end-drawing))
  (close-window)
  0)
```

```
;; rcamera modules
(relative-include "rcamera.h")
(register CameraYaw (λ [(Ptr Camera3D) Float Bool] ()) "CameraYaw")
(defn camera-yaw [camera angle rotate-around-target]
  (CameraYaw (Pointer.address camera) angle rotate-around-target))
(register CameraPitch (λ [(Ptr Camera3D) Float Bool Bool Bool] ()) "CameraPitch")
(defn camera-pitch [camera angle lock-view rotate-around-target rotate-up]
  (CameraPitch (Pointer.address camera) angle lock-view rotate-around-target rotate-up))
```