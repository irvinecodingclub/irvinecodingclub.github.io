---
layout: post
title:  "Python Hands-On Projects"
image: assets/images/icc1.jpg
image2: assets/images/pythonprojects.png
course: true
permalink: /python102
comments: false
excerpt: "Challenge yourself with hands-on Python Projects."
---

| Instructor  | &nbsp;&nbsp;&nbsp;Date&nbsp; | &nbsp;&nbsp; &nbsp;&nbsp;Zoom ID &nbsp; | &nbsp;PASSWORDD  |
| :---        |    :----   |          :--- |  :--- |
| Melody Yu, Annette Lee, Agam Randhawa   | Summer,2021   |&nbsp;&nbsp; 890 1539 2821 &nbsp; &nbsp; |&nbsp; 133428|

<br/>

This is a intermediate level Python class. Students should have a prior knowledge of basic Python, understanding Python topics like loops, variables, functions, sets, and dictionaries. In this class, we will use Python to create several popular games.


## Project 1: Guess the Number

## Guess the Number

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vS1_VSZZrdTYx794AxwPealOLWptqEBn4wgECKWTMcQLlyrU9JFWhz5Wy7gTzvDw5Nsggf_PNmSdlXr/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

{% highlight python linenos %}
import random

def guessthenum(start, stop):
    num = random.randint(start, stop)
    moves = 0
    while True:
        move = input("What do you think the number is?")
        if num > int(move):
            print("Higher\n")
            while True:
                giveup = input("Would you like to give up? (Y or N)")
                if giveup.lower() == "y":
                    return "You have given up"
                elif giveup.lower() == "n":
                    break
                else:
                    print("Hmm... I couldn't understand your answer. \n")
        elif num < int(move):
            print("Lower\n")
            while True:
                giveup = input("Would you like to give up? (Y or N)")
                if giveup.lower() == "y":
                    return "You have given up"
                elif giveup.lower() == "n":
                    break
                else:
                    print("Hmm... I couldn't understand your answer. \n")
        else:
            print("Congrats! You guessed the number in " + str(moves) + " turns. \n")
            break
        moves += 1
guessthenum(input("Start: "), input("Stop: "))


{% endhighlight %}

## Project 2: Rock Paper Scissors

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSgHEXftUWOPpwEy2i2ilS-M1ZsI7eBer08h6M64KUkdCDvyEak1YeMDHYmdkKASWQuBXVKrPvy_FKY/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

This game has two modes - two player, and against the computer. Adjust the parameters (x for amount of rounds) and "on" or "off" for against the computer or against another player, respectively.

{% highlight python linenos %}
import random

def rock_paper_scissors(x, computer = "off"):
  print("Welcome to Rock, Paper, Scissors. \n")
  wins = 0
  totalwins = 0
  if computer.lower() == "on":
    for turn in range(1, x + 1):
      computer_guess = random.choice(["rock", "paper", "scissors"])

      while True:
        your_guess = input("What do you choose?")

        your_guess = your_guess.lower()
        if your_guess == "rock" or your_guess == "paper" or your_guess == "scissors":
          break

      print "The computer chose", computer_guess

      if computer_guess == "rock" and your_guess == "scissors" or computer_guess == "paper" and your_guess == "rock" or computer_guess == "scissors" and your_guess == "paper":
        print("You lost :(")

        totalwins += 1

        if turn == x + 1:
          print("Next round! \n")


      if your_guess == "rock" and computer_guess == "scissors" or \
      your_guess == "paper" and computer_guess == "rock" or \
      your_guess == "scissors" and computer_guess == "paper":
        print("You won!")
        wins += 1
        if turn == x+ 1:
          print("Next round! \n")


      if your_guess == computer_guess:
        print("It is a tie... ")
        if turn == x+ 1:  
          print("Next Round!")


    if totalwins > wins:
      print("You lost! :(")  
    elif totalwins < wins:
      print("You won! :)")
    else:
      print("It's a tie!")

    play_again = input("Would you like to play again? (Yes/No)")
    if play_again.lower() == "yes":
      rock_paper_scissors(x, computer)




  else:

    p1wins = 0
    p2wins = 0
    for turn in range(1, x + 1):    

      while True:
        your_guess = input("What does Player 1 choose?")

        your_guess = your_guess.lower()
        if your_guess == "rock" or your_guess == "paper" or your_guess == "scissors":
          break  
      while True:
        p2_guess = input("What does Player 1 choose?")

        p2_guess = p2_guess.lower()
        if p2_guess == "rock" or p2_guess == "paper" or p2_guess == "scissors":
          break  

      print "The computer choose", computer_guess

      if p2_guess == "rock" and your_guess == "scissors" or \
      p2_guess == "paper" and your_guess == "rock" or \
      p2_guess == "scissors" and your_guess == "paper":                                    
        print("Player 1 lost! Player 2 won!")
        totalwins += 1
        if turn == x + 1:
          print("Next round! \n")


      if your_guess == "rock" and p2_guess == "scissors" or \
      your_guess == "paper" and p2_guess == "rock" or \
      your_guess == "scissors" and computer_guess == "paper":
        print("Player 1 won! Player 2 lost!")
        wins += 1
        if turn == x+ 1:
          print("Next round! \n")


      if your_guess == computer_guess:
        print("It is a tie... ")
        if turn == x+ 1:  
          print("Next Round!")


    if totalwins < wins:
      print("Player 1 won!")    
    elif wins > totalwins:
      print("Player 2 won!")
    else:
      print("It's a tie!")

    play_again = input("Would you like to play again? (Yes/No)")
    if play_again.lower() == "yes":
      rock_paper_scissors(x, computer)



x = 2
rock_paper_scissors(x, "on")
{% endhighlight %}


## Project 3: Pong

The Pong game can be found in the wiki article [here](https://en.wikipedia.org/wiki/Pong).

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTDNDtymJjlEYu-2NnrN1lznlJuLbLIsZlrAyc1xbdJQeAG6QMTK8fKg0l2dXMfYtqGTVaiBD6dNPzO/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

We made this game in python using turtle. To play, use w and s to control the left paddle, and the up and down arrow to move the right paddle.

{% highlight python linenos %}
import turtle

wn = turtle.Screen()
wn.bgcolor("white")
wn.setup(width=800, height=600)
wn.tracer(0)

paddle_a = turtle.Turtle()
paddle_a.speed(0)
paddle_a.shape("square")
paddle_a.color("black")
# paddle_a.shapesize(stretch_wid=5, stretch_len=1)
paddle_a.penup()
paddle_a.goto(-350, 0)

paddle_b = turtle.Turtle()
paddle_b.speed(0)
paddle_b.shape("square")
paddle_b.color("black")
# paddle_b.shapesize(stretch_wid=5, stretch_len=1)
paddle_b.penup()
paddle_b.goto(350, 0)

ball = turtle.Turtle()
ball.speed(0)
ball.shape("circle")
ball.color("black")
ball.penup()
ball.goto(0, 0)
ball.dx = 2
ball.dy = -2


blocka = turtle.Turtle()
blockb = turtle.Turtle()
blockc = turtle.Turtle()
blockd = turtle.Turtle()

blocke = turtle.Turtle()
blockf = turtle.Turtle()
blockg = turtle.Turtle()
blockh  = turtle.Turtle()

# Function
def paddle_a_up():
    y = paddle_a.ycor()
    y += 20
    paddle_a.sety(y)


def paddle_a_down():
    y = paddle_a.ycor()
    y -= 20
    paddle_a.sety(y)


def paddle_b_up():
    y = paddle_b.ycor()
    y += 20
    paddle_b.sety(y)


def paddle_b_down():
    y = paddle_b.ycor()
    y -= 20
    paddle_b.sety(y)

def change_paddle_block(block,x, y):
    block.up()
    block.shape("square")
    block.goto(x, y)

def draw_rec_right():
    y = paddle_a.ycor()
    x = paddle_a.xcor()

    change_paddle_block(blocka, x, y + 20)
    change_paddle_block(blockb, x, y + 40)
    change_paddle_block(blockc, x, y - 20)
    change_paddle_block(blockd, x, y - 40)


def draw_rec_left():
    y = paddle_b.ycor()
    x = paddle_b.xcor()

    change_paddle_block(blocke, x, y + 20)
    change_paddle_block(blockf, x, y + 40)
    change_paddle_block(blockg, x, y - 20)
    change_paddle_block(blockh, x, y - 40)

def block_clear():
    for x in [blocka, blockb, blockc, blockd, blocke, blockf, blockg, blockh]:
        x.clear()

wn.listen()
wn.onkey(paddle_a_up, "w")
wn.onkey(paddle_a_down, "s")
wn.onkey(paddle_b_up, "Up")
wn.onkey(paddle_b_down, "Down")

while True:
    wn.update()

    draw_rec_right()
    draw_rec_left()

    ball.setx(ball.xcor() + ball.dx)
    ball.sety(ball.ycor() + ball.dy)

    if ball.ycor() > 290:
        ball.sety(290)
        ball.dy *= -1

    if ball.ycor() < -290:
        ball.sety(-290)
        ball.dy *= -1

    if ball.xcor() > 390:
        ball.goto(0, 0)
        ball.dx *= -1

    if ball.xcor() < -390:
        ball.goto(0, 0)
        ball.dx *= -1

    if (ball.xcor() > 340 and ball.xcor() < 350) and (
            ball.ycor() < paddle_b.ycor() + 40 and ball.ycor() > paddle_b.ycor() - 40):
        ball.setx(340)
        ball.dx *= -1

    if (ball.xcor() < -340 and ball.xcor() > -350) and (
            ball.ycor() < paddle_a.ycor() + 40 and ball.ycor() > paddle_a.ycor() - 40):
        ball.setx(-340)
        ball.dx *= -1

    block_clear()
{% endhighlight %}


## Project 4: Snake

This game was made in python using turtle. To play, use the arrow keys and guide the snake.

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTq7b72-Cws_iY9nDJU2ihWLsqY3jjCHl70_UcDIKVZznUA3u_YHP2sxF9ksOnLqUU_DatIkYDDtsdm/embed?start=true&loop=true&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>


{% highlight python linenos %}
import turtle
import time
import random

delay = 0.1

score = 0
high_score = 0

wn = turtle.Screen()
wn.bgcolor("blue")
wn.setup(width=600, height=600)
wn.tracer(0)
foodLst = []

head = turtle.Turtle()
head.speed(0)
head.shape("square")
head.color("orange")
head.penup()
head.goto(0,0)
head.direction = "stop"

for x in range(1):
  food = turtle.Turtle()
  food.speed(0)
  food.shape("circle")
  food.color("orange")
  food.penup()
  food.goto(0, 100)
  foodLst.append(food)

segments = []

pen = turtle.Turtle()
pen.speed(0)
pen.shape("square")
pen.color("black")
pen.penup()
pen.hideturtle()
pen.goto(0, 260)
pen.write("Score: 0 High Score: 0", align="center", font=("Comic Sans MS", 24,"normal"))

def move():
  if head.direction == "up":
    y = head.ycor()
    head.sety(y+20)
  if head.direction == "down":
    y = head.ycor()
    head.sety(y-20)
  if head.direction == "left":
    x = head.xcor()
    head.setx(x - 20)
  if head.direction == "right":
    x = head.xcor()
    head.setx(x + 20)

def go_up():
  if head.direction != "down":
    head.direction = "up"
def go_down():
  if head.direction != "up":
    head.direction = "down"
def go_left():
  if head.direction != "right":
    head.direction = "left"
def go_right():
  if head.direction != "left":
    head.direction = "right"


wn.listen()
wn.onkey(go_up, "Up")
wn.onkey(go_down, "Down")
wn.onkey(go_right, "Right")
wn.onkey(go_left, "Left")

while True:

  wn.update()
  """if i % 10 == 0:
    if len(segments) > 1:
      a = segments.pop()
      a.color("blue")
      a.goto(a.xcor(), a.ycor())

      #draw background color in (x,y) , how ???
"""
  if head.xcor() > 290 or head.xcor() < - 290 or head.ycor()> 290 or head.ycor() < -290:
    time.sleep(1)
    head.goto(0,0)
    head.direction = "stop"

    score = 0

    pen.clear()
    pen.write("Score: {} High Score: {}".format(score, high_score), align="center", font=("Comic Sans MS", 24, "normal"))

    for segment in segments:
      segment.goto(1000,1000)

    del segments[:]

    score = 0

    delay = 0.1
    pen.clear()
    pen.write("Score: {} High Score: {}".format(score, high_score), align="center", font=("Comic Sans MS", 24, "normal"))

  for food in foodLst:
    if head.distance(food) < 20:
      colorlst = ["red", "orange", "yellow", "green", "lime green", "blue", "purple", "pink"]
      colorIndex = random.randint(0, 7)
      color = colorlst[colorIndex]
      x = random.randint(-290, 290)
      y = random.randint(-290, 290)
      food.goto(x, y)



      new_segment = turtle.Turtle()
      new_segment.speed(0)
      new_segment.shape("square")
      new_segment.color(color)
      new_segment.penup()
      segments.append(new_segment)

      score += 10

      delay -= 0.001

      if score > high_score:
        high_score = score

      pen.clear()
      pen.write("Score: {} High Score: {}".format(score, high_score),align="center",  font=("Comic Sans MS", 24,"normal"))
  for index in range(len(segments) -1, 0, -1):
    x = segments[index-1].xcor()
    y = segments[index-1].ycor()
    segments[index].goto(x,y)

  if len(segments) > 0:
    x = head.xcor()
    y = head.ycor()
    segments[0].goto(x,y)

  move()

  for segment in segments:
    if segment.distance(head) < 20:
      time.sleep(1)
      head.goto(0,0)
      head.direction = "stop"

      score = 0
      pen.clear()
      pen.write("Score: {} High Score: {}".format(score, high_score), align="center",
            font=("Comic Sans MS", 24, "normal"))

      for segment in segments:
        segment.goto(1000, 1000)

      del segments[:]

      score = 0

      delay -= 0.001

      pen.clear()
      pen.write("Score: {} High Score: {}".format(score, high_score), align="center",
            font=("Comic Sans MS", 24, "normal"))

  time.sleep(delay)


wn.mainloop()


{% endhighlight %}
