---
aliases: 
created: 2022-04-30, 7:32:57 am (Saturday, April 30th)
updated: 2022-04-30, 7:35:44 am (Saturday, April 30th)
---
The Teensy has two life-cycle functions: `setup` and `loop`.
`setup` is for what you're thinking: configuring the pins of the board prior to running the main program.
`loop` is the main program.
It's called `loop` because that function is ran over and over for as long as the board has power.
In an interesting way, it's like a game loop!