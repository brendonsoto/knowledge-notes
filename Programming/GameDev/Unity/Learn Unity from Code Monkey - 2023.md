---
tags:
  - unity
  - tutorial
created: Sunday, January 28, 2024 8:14 PM
created_at: 2024-01-28T20:14:41-05:00
---
[YouTube](https://www.youtube.com/watch?v=AmGSEH7QcDg)

This video is a tutorial that takes you through building an Overcooked clone.

## Prerequisite videos

### How to make a game...

[Youtube](https://www.youtube.com/watch?v=hKXsL7XNa9M)

#### Render Pipelines

This is part of configuring a project. The options are:
- URP (Universal Rendering Pipeline) - Use this for the majority of projects
- HDRP (High Definition Rendering Pipeline) - This seems aimed at creating High-Def games or animations?
- Legacy (no acronym) - Unity's legacy rendering pipeline. You probably don't want to use this.

#### Starter assets

[https://assetstore.unity.com/essentials](https://assetstore.unity.com/essentials)

#### Loading assets

I think you just drag and drop the assets into a folder in your project (in the _Project_ window) and double click the assets file.

If you see loads of **pink**, that means there's a shader error. This can happen because assets could've been built (not sure if that's the right term) using a different render pipeline than the one you've selected for your project. To **fix** this, use the toolbar to navigate to Window > Rendering > Render Pipeline Converter, check off the "Upgrade Materials" checkbox, and click "Convert Assets".

### Learn Unity in 17 Minutes

- **Game Object** - The building block within Unity. Everything within a Unity game consists of game objects.
- **Component** - Think of this as a unit of behavior. For example, you can create an empty game object and it will come with just transformation properties (position, rotation, scale). A "mesh" component can be added to it and a "mesh renderer" component can be added to make the "mesh" displayed. (I guess a mesh is like a skin for a game object) No, I'm wrong. A "material" with a "texture" is applied to a "mesh" to create a textured object. That seems complex...
- For **physics**, the "rigidbody" component was mentioned.
    - It looks like a "collider" component can be added with a "rigidbody" component to provide a shape for physics to be applied to. For example, a "sphere collider" would be applied to a game object that has a "sphere mesh" so the game object would behave like a sphere and not like another shape, like a square.
- To **log messages**, use `Debug.Log("my message");`
- For **2D** use "sprite Renderer" instead of a "mesh renderer" and swap the **camera** game object's _Projection_ property from "perspective" to "orthographic"
- **Scenes** are how you organize your game into different segments, like a start menu, the main game, other menus.


### Learn C# basics in 10 minutes

[YouTube](https://www.youtube.com/watch?v=IFayQioG71A)

- ~~Creating a console app in Visual Studio is the quickest way to mess around with C#~~
    - Maybe it is, but it involves downloading the .NET core runtime.
- **Collections** is a term to refer to _arrays_ and _lists_
    - Array: `int[] pointsEarnedPerRound = new int[10];`
        - This sets all values to zero
        - Arrays are **fixed**
        - Alternative creation with set values: `int[] faveNums = new int[] { 3, 7, 17, 333 }`
    - List: `List<int> pointsEarnedPerRound = new List<int>();`
        - Lists are **dynamic**, meaning it's easy to grow or shrink them.
        - You can set initial values the same way as with an array (with `{ 1, 2, ... }`)
- **Loops**
    - `foreach (<type> i in <var>) { ... }` seems to be the idiomatic way
    - There's the classic for: `for (int i = 0; i < myList.Count; i++) { ... }`
    - While loops: `while (cond) { ... }`
    - Do While: `do { ... } while (cond);`
- **Comments**
    - `// single line comment`
    - `/* multi line comment */`
- **Enums**
    - `enum PlayerState { Idle, Attacking }`
    ```
    enum PlayerState {
        Idle,
        Attacking
    }
    ```
    - They are useful when combined with `switch` statements

#### Aside: What's the difference between Visual Studio and Visual Studio Code?

Visual Studio is a whole IDE whereas Visual Studio Code is just a text editor.