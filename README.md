from tkinter import * 
from math import *
def click(event):
    global scvalue
    text=event.widget.cget("text")
    if text=="=":
        if scvalue.get().isdigit():
           value=int(scvalue.get())
        else:
            try:
               value =eval(screen.get())
               scvalue.set(value)
               screen.update()

            except Exception as e:
              print(e)
            value="error"

        
    elif text== "C":
        scvalue.set("")
        screen.update()
    else:
        scvalue.set(scvalue.get()+ text)
        screen.update()

root=Tk()
root.geometry("500x450")
# root.maxsize("500x450")
# root.minsize("500x450")
root.title(" CALCULATOR ")
# root.wm_iconbitmap("1.ico")


scvalue=StringVar()
scvalue.set("")
screen=Entry(root,textvariable=scvalue,font="lucida 30 bold")
screen.pack(fill=X,ipadx=8,padx=10,pady=10)

f1=Frame(root,bg="grey")
f1.pack()

buttons=["9","8","7",]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=LEFT,padx=12,pady=8)
   b1.bind("<Button-1>",click)


f1=Frame(root,bg="grey")
f1.pack()

buttons=["6","5","4",]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=LEFT,padx=12,pady=8)
   b1.bind("<Button-1>",click)


f1=Frame(root,bg="grey")
f1.pack()

buttons=["3","2","1",]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=LEFT,padx=12,pady=8)
   b1.bind("<Button-1>",click)

f1=Frame(root,bg="grey")
f1.pack()

buttons=["0","*","-",]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=LEFT,padx=14,pady=8)
   b1.bind("<Button-1>",click)
f1=Frame(root,bg="grey")
f1.pack()

buttons=["/","C","%",]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=RIGHT,padx=11,pady=8)
   b1.bind("<Button-1>",click)

f1=Frame(root,bg="grey")
f1.pack()

buttons=["+",".","="]
for i in buttons:

   b1=Button(f1,text=i,padx=25,pady=12,font="lucida 20 bold")
   b1.pack(side=LEFT,padx=12,pady=8)
   b1.bind("<Button-1>",click)


root.mainloop()
