.. _part3:

Part 3
======

In part 3 we'll add images for the quiz answers and show them on the screen so that
the player can choose them in the quiz.

Adding answer images
--------------------

Above your draw function add this line to store our animal answers: ::

  answer_images = [ ]

Now go find some animals, I would suggest we start with a frog and a newt.
E.g. https://www.google.com/search?q=frog+uk

Save the image to `mu_code/images` as before with nice short names.

Now update your `answer_images` with each image you find. E.g. I have this: ::

  answer_images = ['newt.jpg', 'frog.jpg', ]

Now we only want to draw the animals if we've started playing. And we need to draw each image in turn and draw it across the screen.

So add this code inside draw indented 4 spaces: ::

  if state == 'play':
      for x,i in enumerate(answer_images):
          screen.blit(i, (x*150, 25))
          screen.draw.text(str(x+1), (x*150, 25), color='white', fontsize=40)

Now test. Are the images are too big?
OK, so make each of your images the same size, maybe 200px across?

  
Resizing images
---------------

Do you know how to resize them? You probably have a program to do this
already on your computer.

On a Mac
........

You can use Preview. 

* Open the image in Preview first
* There's a tiny A icon - Show Markup Toolbar
* Click that then you can resize and save.

On a Windows computer
.....................

[To be completed]

Overlapping images
------------------
  
Are you happy with your images now? 

* they are overlapping
* Do you see the bit in your code `x*150` ?
* Try numbers bigger than 150 to fix this


Next up...
----------

In part four of this tutorial we'll add the baby animals: :ref:`part4`.
     


