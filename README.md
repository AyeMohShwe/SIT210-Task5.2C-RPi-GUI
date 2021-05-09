from tkinter import *
import tkinter.font
from gpiozero import LED
import RPi.GPIO as GPIO
RPi.GPIO.setmode(RPi.GPIO.BCM)
RPi.GPIO.setmode(RPi.GPIO.BOARD)

RLed = LED(14)
GLed = LED(15)
BLed = LED(18)

win = Tk()
win.title("LED GUI")
myFont = tkinter.font.Font(family = 'Helvetica', size = 12, weight = "bold")

def ledToggle():
    var = val.get()
    if  var == 1:
       RLed.on()
       GLed.off()
       BLed.off()
    elif var == 2:
       RLed.off()
       GLed.on()
       BLed.off()
    else:
       RLed.off()
       GLed.off()
       BLed.on()
def close():
       GPIO.cleanup()
       win.destroy()

RButton = Button(win, text = 'RED', font = myFont, variable = val, value = 1,  $
RButton.grid(row=0, column=1)
GButton = Button(win, text = 'Green', font = myFont, variable = val, value = 2,$
GButton.grid(row=1, column = 1)

BButton = Button(win, text = 'Blue', font = myFont, variable = val, value = 3, $
BButton.grid(row=2, column=1)

CloseButton = Button(win, text = 'Close', font = myFont, command = close)
CloseButton.grid(row = 2, column = 1)

win.protocol("WM_DELETE_WINDOW", close)
win.mainloop()


       
