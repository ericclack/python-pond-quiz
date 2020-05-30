.. _part1:

Part 1
======

In part 1 we're going to create the game window and add a background. 

Create the game window
----------------------

Start up your Mu editor and click *New* to start a new, empty script.

Type in the following code: ::

  TITLE = 'Pond Quiz'
  WIDTH = 800
  HEIGHT = 600

Try not to just copy and paste, because the typing practice will
really help you remember how to program.

When you press *Play* you'll have to save your script and give the file a name. Check that it saves in `mu_code` directory -- it should do this for you.

You shuld see a black screen with the title *Pond Quiz*.

Add the background
------------------

Now go onto your favourite image search and look for a suitable
background. I've chosen an underwater scene, but you could choose
anything that fits with your quiz.

Save your image into :code:`mu_code/images` and give it a nice short
name such as :code:`pond.jpg`.

Now add this code to your script: ::

  def draw():
    screen.blit('pond.jpg', (0, 0))

Test your program, you should see your background. 


Next up...
----------

In part two of this tutorial we'll add some welcome text: :ref:`part2`.

