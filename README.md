# raylib4carp
 Raylib Binding for personal use

# Notice
- Carp version is 0.6.0, Raylib version is 6.2.
- Implementation:
 * [x] raylib.h
 * [ ] rlgl.h
 * [ ] raymath.h
- `prn` warning: I don't know how to fix it.
- Fixed-length array is defined to `(Ptr t)` with length comment.
- `typedef A *B;`: No type alias in Carp. `(typedef A (Ptr B))` doesn't work. Following type is not available now. Use the right side instead:
 * ModelAnimPose: (Ptr Transform)