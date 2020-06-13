.. _part5:

Part 5
======

In part 5 we'll add an end to the quiz. 

  This part is very rough and includes chat sessions from our Coder Dojo session. I'll
  fix these soon so that it is easier to follow. 
  
  
What's the score?
-----------------

Let's add a score. We can increase it when the player gets an answer correct and
reduce it when they get one wrong.

Add this line near the top of your code under your questions array: ::

  score = 0

Now in :code:`on_key_up` lets increase or decrease it. Change your code to add
these new lines: ::

  def on_key_up(key):
      global state, score        # <--- added score
      if key == keys.SPACE:
          state = 'play'

      if state == 'play' and keys.K_0 <= key <= keys.K_9:
          n,q = questions[0]
          answer = key.value - keys.K_0.value - 1
          if answer == n:
              print("Correct!")
              questions.pop(0)
              score += 1         # <--- New line
          else:
              print("Wrong, try again")
              score -= 1         # <--- New line
          print(score)           # <--- New line

You don't need to add the comments starting with :code:`#`.

Now test again, making sure to get some answers wrong to see the score change.

The end sequence
----------------

Currently the code ends with an error after the last question, let's fix this.

At the end of your :code:`on_key_up` function add this code to test when there
are no more questions: ::

  # No more questions left
  if not questions:
      state = 'end'

Now we can add an end sequence. In :code:`draw` add this code... ::

  # End sequence
  if state == 'end':
      screen.draw.text(
          "The end",
          color='white',
          midtop =(WIDTH/2, HEIGHT/2 - 50),
          fontsize=70,
      )

      screen.draw.text(
          "You scored %s" % score,
          color='white',
          midtop =(WIDTH/2, HEIGHT/2 + 50),
          fontsize=40,
      )

We can add more too, let's tell the user how they did: ::

      if score == len(question_images):
          message = "You are a genius!"
      elif score < 0:
          message = "Oh dear!"
      else:
          message = "Hope you do better next time"

      screen.draw.text(
          message,
          color='white',
          midtop =(WIDTH/2, HEIGHT/2 + 150),
          fontsize=40,
      )      


Right or wrong?
---------------

Let's tell the user in the game screen when they get something right or wrong.

[todo]

