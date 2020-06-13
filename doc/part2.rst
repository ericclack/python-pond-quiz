.. _part2:

Part 2
======

In part 2 we're going to add a welcome message and wait for the player to press space to start. 

Adding the welcome message
--------------------------

Add this code to your :code:`draw` function: ::

  screen.draw.text(
    "Welcome to the Pond Quiz!",
    color='white',
    midtop =(WIDTH/2, HEIGHT/2 - 50),
    fontsize=70,
    )

And we can also tell the player how to start: ::

  screen.draw.text(
    "Press space to start",
    color='white',
    midtop =(WIDTH/2, HEIGHT/2 + 50),
    fontsize=40,
    )

Have a play with those numbers to make the text bigger or change its position on the screen. You can also change the colour, see the `Pygame Colour List`_.

Waiting for space
-----------------

Add a new variable called :code:`state` -- put this just under :code:`HEIGHT`: ::

  state = 'start'

Now a tricky bit... Wrap your two :code:`screen.draw.text` statements with the following line: ::

  if state == 'start':

Wrap means: add this :code:`if` statement above, then indent the two :code:`screen.draw.text` blocks to the right so that they are inside the :code:`if` statement.

So you code should look like this: ::

  if state == 'start':
      screen.draw.text(
        "Welcome to the Pond Quiz!",
        color='white',
        midtop =(WIDTH/2, HEIGHT/2 - 50),
       fontsize=70,
      )

      screen.draw.text(
        "Press space to start",
        color='white',
        midtop =(WIDTH/2, HEIGHT/2 + 50),
        fontsize=40,
      )

Check that your game still works and that the background and text still display OK.

OK, now let's spot the user pressing space and remove the welcome message...

Add this new function at the end of your code: ::

  def on_key_up(key):
      global state
      if key == keys.SPACE:
          state = 'play'

Time to test again. Pressing Space should remove the welcome message ready for our first question. 


Next up...
----------

In part three of this tutorial we'll add some animal images: :ref:`part3`.

.. _`Pygame Colour List`: https://github.com/pygame/pygame/blob/master/src_py/colordict.py#L23
