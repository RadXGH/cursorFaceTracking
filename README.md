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

##The Logic

The program captures a user's face with a normal webcam. It uses the face recognition classifier (haarcascade_frontalface_default.xml) provided. Program doesn't work with multiple faces in 1 frame.
For each frame, the program moves the cursor accordingly by adding a few pixels into it's current position.
Perhaps it's easier to understand using a picture:
