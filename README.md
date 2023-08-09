# TurtleRacing
About this project  we write a code is a simple racing game that uses the Python turtle module.
# required modules
import turtle
from turtle import * 
from random import randint

# classic shape turtle
speed(0)
bgcolor("yellow")
penup()
goto(-140, 140)

# racing track

for step in range(18):
  write(step, align ='center')
  right(90)
  
  for num in range(8):
    penup()
    forward(10)
    pendown()
    forward(10)
    
  penup()
  backward(160)
  left(90)
  forward(20)

# first player details
player_1 = Turtle()
player_1.color('green')
player_1.shape('turtle')

# first player proceeds to racing track
player_1.penup()
player_1.goto(-160, 100)
player_1.pendown()

# 360 degree turn
for turn in range(10):
  player_1.right(36)

# second player details
player_2 = Turtle()
player_2.color('blue')
player_2.shape('turtle')

# second player enters in the racing tr
player_2.penup()
player_2.goto(-160, 40)
player_2.pendown()

# 360 degree turn
for turn in range(72):
  player_2.left(5)

# turtles run at random speeds
for turn in range(100):
  player_1.forward(randint(1, 6))
  player_2.forward(randint(1, 6))

# check if player_1 reached the finish line
if player_1.xcor() >= 140:
  # declare player_1 as the winner
  winner = "green"
  # give the winner a "won" message
  write("The winner is: green", align="center", font=("Courier", 20, "bold"))

# check if player_2 reached the finish line
elif player_2.xcor() >= 140:
  # declare player_2 as the winner
  winner = "blue"
  # give the winner a "won" message
  write("The winner is: blue", align="center", font=("Courier", 20, "bold"))

# create a start button
def start_button():
  global running
  running = True

# create a button object
button = turtle.button(-140, 120, "Start", start_button)

# start the game when the button is clicked
button.onclick()
turtle.done()
