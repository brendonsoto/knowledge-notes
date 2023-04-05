---
created_at: 2023-mar-31T22:48:42 (whatever timezone South Dakota is)
---
## Glossary
### Atlas
A collection of images used for textures and animations. On why a collection instead of a sprite sheet:
> Defold uses atlases instead of single image files for performance and memory reasons.

### Collection
Holds 

### Component
A 

### Game Object
I'm guessing object here is used assuming the context of Object Oriented Programming. I wonder if Class would be a better name.

_Something_ that has:
- an _id_: I guess this is to distinguish one object from another
- a _position_: I'm guessing where the audio/visual/logic event is to be
- a _rotation_:
- a _scale_: I guess this adds depth in the sense of making some things seem bigger than others

**Note**: Position has a z-index concept similar to CSS.

### Game Script

### Tile Map
An image representing your game's world. It's made up of smaller images derived from a [Tile Source](Tech/Software/GameDev/Defold.md#Tile%20Source).

### Tile Source
An image that is used to build out the [Tile Map](Tech/Software/GameDev/Defold.md#Tile%20Map). Defold creates a grid over the image so you can pick different parts of the image while building out your map. It's like using the original image to create the building blocks to make a new one.