# Tkinter_Calculator_App
#step1: import tkinter
from tkinter import *

#step2: gui interaction
window = Tk()

#step3: adding inputs
window.title("Calculator")
window.geometry("500x500")

e = Entry(window , width = 50 , borderwidth = 5)
e.place(x = 10 , y = 10)

def click(num):
    result = e.get()
    e.delete(0, END)
    e.insert(0, str(result) + str(num))

b = Button(window , text = "1" , width = 12 , command = lambda: click(1))
b.place(x=20 , y=60)

b = Button(window , text = "2" , width = 12 , command = lambda: click(2))
b.place(x=90 , y=60)

b = Button(window , text = "3" , width = 12 , command = lambda: click(3))
b.place(x=180 , y=60)

b = Button(window , text = "4" , width = 12 , command = lambda: click(4))
b.place(x=20 , y=120)

b = Button(window , text = "5" , width = 12 , command = lambda: click(5))
b.place(x=90 , y=120)

b = Button(window , text = "6" , width = 12 , command = lambda: click(6))
b.place(x=180 , y=120)

b = Button(window , text = "7" , width = 12 , command = lambda: click(7))
b.place(x=20 , y=180)

b = Button(window , text = "8" , width = 12 , command = lambda: click(8))
b.place(x=90 , y=180)

b = Button(window , text = "9" , width = 12 , command = lambda: click(9))
b.place(x=180 , y=180)

b = Button(window , text = "0" , width = 12 , command = lambda: click(0))
b.place(x=20 , y=240)

def add():
    n1 = e.get()
    global i
    global math
    math = "addition"
    i = int(n1)
    e.delete(0, END)

b = Button(window , text = "+" , width = 12 , command = add)
b.place(x=90 , y=240)

def sub():
    n1 = e.get()
    global i
    global math
    math = "subtraction"
    i = int(n1)
    e.delete(0, END)

b = Button(window , text = "-" , width = 12 , command = sub)
b.place(x=180 , y=240)

def div():
    n1 = e.get()
    global i
    global math
    math = "division"
    i = int(n1)
    e.delete(0, END)

b = Button(window , text = "/" , width = 12 , command = div)
b.place(x=20 , y=300)

def mult():
    n1 = e.get()
    global i
    global math
    math = "multiplication"
    i = int(n1)
    e.delete(0, END)

b = Button(window , text = "*" , width = 12 , command = mult)
b.place(x=90 , y=300)

def equal():
    n2 = e.get()
    e.delete(0, END)
    if math == "addition":
        e.insert(0, i + int(n2))
    elif math == "subtraction":
        e.insert(0, i - int(n2))
    elif math == "division":
        e.insert(0, i / int(n2))
    elif math == "multiplication":
        e.insert(0, i * int(n2))

b = Button(window , text = "=" , width = 12 , command = equal)
b.place(x=180 , y=300)

def clear():
    e.delete(0, END)

b = Button(window , text = "Clear" , width = 12 , command = clear)
b.place(x=20 , y=350)


#step4: main loops
mainloop()
