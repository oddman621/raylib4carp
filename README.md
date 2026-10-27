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
* Focused on implementation over convenience.

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
