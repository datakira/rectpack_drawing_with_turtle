# Rectpack_drawing_with_turtle

I forked the project 'rectpack' from here :

https://github.com/secnot/rectpack


Using the result of this code, **this is code for drawing rectangles with Turtle**.


---

The example of the Drawings is this:

![캡처9](https://user-images.githubusercontent.com/65406000/117544987-cb59b380-b05e-11eb-83de-6c9600cb46a1.JPG)


Set the screen
```python
def set_screen():
    sc = turtle.Screen()
    sc.bgcolor("white")
```

Change color of the turtle
```python
def change_color():
    R = random.random()
    B = random.random()
    G = random.random()

    turtle.color(R, G, B)
```

Move the turtle
```python
def draw_rectangle(x, y, width, height):
    turtle.shape("classic")
    turtle.width(2)
    turtle.speed(0)
    turtle.up()
    turtle.goto(x, y)
    turtle.down()
    forward(width)          
    turtle.left(90)
    forward(height)
    turtle.left(90)
    forward(width)
    turtle.left(90)
    forward(height)
    turtle.left(90)
```

Draw rectangles with turtle
```python
set_screen()

tmp = -1
for i in all_rects:
    if tmp != i[0]: # If rect index has changed, draw (new) bin. If not, don't have to draw the bin again.
        tmp = i[0]
        turtle.color('black')
        draw_rectangle(0, 0, int(bins[tmp][0]), int(bins[tmp][1]))
        print('{0} th bin Drawing Finished'.format(tmp))
    
    x = int(i[1])
    y = int(i[2])
    width = int(i[3])
    height = int(i[4])
    change_color()
    draw_rectangle(x, y, width, height)
    print('width:{0},\theight:{1}\tRectangle was put in {2} th bin - DONE'.format(width, height, tmp))

turtle.exitonclick()
```
