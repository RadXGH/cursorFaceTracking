# Cursor Face Tracking
_I was bored and made this :D_

## Intro

I coded a program to control the cursor of a computer with tracking a person's face using a normal webcam.

This program was coded in Python 3.9.5 using several modules:
- OpenCV (version 4.5.2)
- NumPy (version 1.20.3)
- Pynput (version 1.6.8)

Converted the main.py file into main.exe with PyInstaller.
Program uses haarcascade_frontalface_default.xml classifier for face recognition.

## The Logic

The program captures a user's face with a normal webcam. It uses the face recognition classifier (haarcascade_frontalface_default.xml) provided. Program doesn't work with multiple faces in 1 frame. For each frame, the program moves the cursor accordingly by adding a few pixels into it's current position.

Perhaps it's easier to understand using a picture:

_this picture can be used to understand using the explanation provided at the bottom or to understand while reading the code_

![algo pic small](https://user-images.githubusercontent.com/85069947/123402205-b1097400-d5d1-11eb-96dc-156cbac943d7.jpg)

Color coded:
- Green Dots: known coordinates of the screen.
- Yellow Dot: coordinate of the middle of the face frame (nose).
- Red Lines: dividing lines of the screen.

If the Yellow Dot is ...
1. at the middle of the Red Lines, the cursor doesn't move.
2. at the middle top of the Red Lines, the cursor moves upward.
3. at the middle bottom of the Red Lines, the cursor moves downward.
4. at the middle left of the Red Lines, the cursor moves left.
5. at the middle right of the Red Lines, the cursor moves right.
6. at the I mark/space, the cursor moves diagonally upward and to the left.
7. at the II mark/space, the cursor moves diagonally upward and to the right.
8. at the III mark/space, the cursor moves diagonally downward and to the left.
9. at the IV mark/space, the cursor moves diagonally downward and to the right.

## Outro

Requirements for running the program:
- normal webcam
- keyboard
- computer that can run .exe files (or .py file if the user know how to run it)

Running the program:
- simply open the main.exe file.
- move the green square outside the blue rectangle to move the cursor by the movement of the user's face.
- press p on your keyboard to pause tracking.
- press q on your keyboard to exit the program.

### Important Notes
```
faceCascade = cv2.CascadeClassifier('D:/Coding/Python 3/Cursor control with face recog/classifier/haarcascade_frontalface_default.xml')
```
- The above code must be modified and changed into the exact path of the haarcascade_frontalface_default.xml file in your computer.
```
cv2.VideoCapture(0)
```
- The above code might need to be modified for using different sources of webcams (i.e. having multiple webcams connected or using obs virtual webcam plugin (won't work with the vanilla virtual webcam)).
```
camSizeX = 960
camSizeY = 540
```
- The size/resolution of the frame might need to be modified if the blue rectangle isn't in the middle of the screen using the code provided above.
```
midOfScreenX = camSizeX / 2
midOfScreenY = camSizeY / 2
```
- The size of the blue rectangle can be modified using the code above.
```
moveX = 30
moveY = 30
```
- How fast/far the cursor changes position can be modified using the code above.
