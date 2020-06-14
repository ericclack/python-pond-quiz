.. _part3:

Part 3
======

In part 3 we'll add images for the quiz answers and show them on the
screen so that the player can choose them in the quiz.

Adding answer images
--------------------

Above your draw function add this line to store our animal answers; it
creates an empty list: ::

  answer_images = [ ]

Now go find some animals, I would suggest we start with a frog and a newt.
E.g. https://www.google.com/search?q=frog+uk

Save the image to `mu_code/images` as before with nice short names.

Now update your `answer_images` list with each image you find, wrapped
in quotes. E.g. I have this: ::

  answer_images = ['newt.jpg', 'frog.jpg', ]

Now we only want to draw the animals if we've started playing. And we
need to draw each image in turn and draw it across the screen.

So add this code inside your :code:`draw` function: ::

  if state == 'play':
      for x,i in enumerate(answer_images):
          screen.blit(i, (x*150, 25))
          screen.draw.text(str(x+1), (x*150, 25), color='white', fontsize=40)

Now it's time to test. Are the images too big? OK, so we need to make
each of your images the same size, maybe 200px across?

  
Resizing images
---------------

Do you know how to resize images? You probably have a program to do this
already on your computer...

On a Mac
........

You can use the *Preview* application:

* Open the image in Preview first -- try double clicking the image to do this
* Now toose *Adjust Size* from the *Tools* menu
* Resize your image, and finally save the image.

On a Windows computer
.....................

You can use the *Paint* application:

* Open Paint, then open your image with the menu *File* and then *Open*
* On the Home tab of the Paint toolbar, click the *Resize* button
* Resize your image, and finally save the image.

Overlapping images
------------------
  
Once you've resized your images it is time to test again. Are you
happy with your images now? They could be overlapping each other.

To fix the overlapping:

* Find the two places in the code that have :code:`x*150`
* Try numbers bigger than :code:`150` to fix this.


Next up...
----------

In part four of this tutorial we'll add the baby animals: :ref:`part4`.
     


