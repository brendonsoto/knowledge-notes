---
aliases: 
created: 2022-05-03, 10:00:18 pm (Tuesday, May 3rd)
updated: 2022-05-04, 10:35:59 pm (Wednesday, May 4th)
---
[Tutorial page](https://www.pjrc.com/teensy/tutorial3.html)

This one was frustrating.
I still had my *USB Type* set to **Raw HID** because I didn't realize that was only for the *very first time running the teensy*.
I was wondering why I only saw output one time.
Turns out I didn't have the configuration correct in the IDE.
First I had to go to *Tools* > *USB Type* > set to **Serial**.
Then I had to navigate to *Tools* > *Port* > and select one of the teensy ports.
Only then could I finally see output.

It's neat that there's a *pull up resistor* in the board.

## Questions
### What is baud rate?

### Why is a pull up resistor necessary?