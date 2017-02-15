# The All Seeing Pi (Part 2 - Software)

In this resource you will make a tweeting touch screen photo booth using a Raspberry Pi.

## Test the buttons

1. With the hardware set up, we can begin to program the software that will make everything work. To begin, open the file explorer, then right click on a blank space inside the file explorer window.

  ![File Explorer](images/file-explorer.png)

1. Select `Create new` and then click `Folder`

  ![Create folder menu](images/create-folder.png)

1. Type in the name of the folder where you will store the code and the photographs. We chose to call ours `allseeingpi`. Make a note of the path to this folder which is displayed in the bar at the top, which should be `/home/pi/allseeingpi`

1. From the "Programming" menu, open up "Python 3"

  ![Open Python 3](images/python3-app-menu.png)

1. Create a new Python file by clicking on `File` > `New File`.

1. Click on `File` > `Save` and save your file into the `allseeingpi` folder you just created, with the filename `allseeingpi.py`.

1. We will need the `gpiozero` library. At the start of your Python file add an import statement:

```python
from gpiozero import Button
```

1. Next we will set up the buttons. On the [previous worksheet](worksheet.md) we wired our buttons to pins 23 and 25. Let's go ahead and set both buttons up.

  ```python
  next_overlay_btn = Button(23)
  take_pic_btn = Button(25)
  ```

1. Now we will use gpiozero to tell the buttons what to do when pressed. In the code below, `next_overlay` and `take_picture` are functions which will be called when the corresponding button is pressed:

  ```python
    next_overlay_btn.when_pressed = next_overlay
    take_pic_btn.when_pressed = take_picture
  ```

1. We will write these two functions so that the buttons know what to do when they are pressed. Functions are usually written at the start of a program immediately after the `import` statements. Add the functions, but with some placeholder code to just print a message when they are pressed, so we can test them.

  ```python
  def next_overlay():
    print("Next overlay")

  def take_picture():
    print("Take a picture")
  ```

1. Press `F5`, save and run your program. Try pressing each button and check that a different message pops up for each in the Python shell.

    ![Test the buttons](images/test-buttons.png)

## Add fun overlays

1. The All Seeing Pi isn't a normal photo booth. The second button we set up, `next_overlay_btn`, is used to change between 'overlays' or funky additional pictures to make your photos look cool. Here is an example of a picture taken with an overlay:

    ![Rik with pigtail overlay](images/rik-picture.png)

    You can make your own overlays or we have provided some ready made ones that you can download


## Change overlays with a button

## Take a picture when button pressed

from picamera import PiCamera

## Tweet picture

## Create a GUI