.. _part4:

Part 4
======

In part 4 we'll add images for the quiz questions and show them one at a time.

  This part is very rough and includes chat sessions from our Coder Dojo session. I'll
  fix these soon so that it is easier to follow. 

Whose baby is this?
-------------------

Look in `draw` function, do you see the line that says `if state == 'play':`

So under the answer images put this line: ::

  screen.draw.text("Whose baby is this?", (25, HEIGHT/2), color='white', fontsize=40)

But... What about the indenting? What do we line it up with?
Try it and see what happens. We can then use the pad to fix any problems.

OK, so now we need to show the question, the right image for the next question.

There are a few lines to add...

Under your baby_animals list at the top, add this line: ::
  
  questions = list(enumerate(question_images))

This turns your list of images into a list of question numbers and
images, so 1, frog; 2, newt, etc.

Next, under Whose baby is this? add these lines: ::

  n,q = questions[0]
  screen.blit(q, (25, HEIGHT/2 + 50))

So now I think we have to let the user answer each question.

Answer the question
-------------------

Do you see where we spot the SPACE key? What function is it in?

`on_key_up`

Yes. OK a few lines to add now...

What we are doing is watching for the user's key presses.

They can press the number keys to answer each question

So first line to add at the end of that function is... ::

  if state == 'play' and keys.K_0 <= key <= keys.K_9:

What do you think this does: `keys.K_0 <= key <= keys.K_9`

What would this do: ::

  a = 5
  if 1 < a < 10:
    print("Hello!")

(This is a simpler version)

If a is between 1 and 10 then print hello.

OK, so back to our code

That line checks to see if the key pressed is between 1 and 9

Now add these lines inside the if-statement: ::

  n,q = questions[0]
  answer = key.value - keys.K_0.value - 1

Great. So here's where we are:

If the user presses a number key, we get the next question number in n

We work out what answer they've given and store it in answer

We now need to test if they got the answer correct

Add this code next: ::

  if answer == n:
     print("Correct!")
     questions.pop(0)
  else:
     print("Wrong, try again")

Now time to test the quiz! Check in the console as you answer each question.


Add more animals
----------------

Now might be a good time to add more animals.

Try dragonfly: their babies are really cool!

Or caddisfly: their babies make little stone shelters to live in.

You'll end up with pairs of images: the answer one (the adult) and the question one (the baby). Put these into the two arrays you have at the top of your code: ::

  answer_images = ['newt.jpg', 'frog.jpg', ]
  question_images = ['baby_newt.jpg', 'tadpoles.jpg', ]

If you now press *Play* those new animals should just appear. 
  
Next up...
----------

In part five of this tutorial we'll do the end quiz sequence. :ref:`part5`.
     


