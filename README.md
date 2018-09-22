# Work 12
New MDL commands to implement:
* frames
* basename
* vary

#### Animation Features:
* Set frames and basename
* Handle erros as needed
* Go through the operations list a second time and look for the vary command
* Populate a table that has an entry for each frame, and in each frame it has a value for each knob

* Handle errors as needed
* Perform the normal interpreting/drawing steps that are currently working, with the following additions if animation code is present. 
* First, look at the table of knob values (set in the second step) and set each knob in the symbol table to the appropriate value.
* Run the normal commands
* At the end of the loop, save the current screen to a file, the file should have the basename followed by a number, so that animate will work correctly. 

* When you are done with each frame loop, don't forget to reset the screen, origin stack and any other pieces of data that are specific to a given frame
* Once you have all the files created, you can generate the animation using imagemagick's animate and convert commands:
animate
* Will display multiple single image files in succession as a single animation, with a default frame rate of 100 frames per second, by using the -delay option, you can change the fps ( -delay x will set the frame rate to 100/x fps )
``` 
$ animate -delay 10 animations/orb*
```
* Convert can, like animate, take a number of frames and animate them, but instead of displaying the animation, it will combine them into a single animated gif file. Note that the only image format that can use animation is gif.
``` $ convert -delay 10 animations/orb* orb.gif ``` will create a single animated gif called orb.gif
*In python and c, I've included a make_animation function in display.c/py that will generate the animation for you.
