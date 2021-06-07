```python
#Shweta's Assignment
#Virtual Shopping CART(Dry Fruits)
```


```python
pip install tkiter

```

    Note: you may need to restart the kernel to use updated packages.
    

    'C:\Users\SHWETA' is not recognized as an internal or external command,
    operable program or batch file.
    


```python
from tkinter import *

root = Tk()
root.geometry('800x800')
root.title("Sign up Page")

label_0 = Label(root, text="Sign up Page",width=20,font=("bold", 20))
label_0.place(x=90,y=53)


label_2 = Label(root, text="Email",width=20,font=("bold", 10))
label_2.place(x=80,y=130)

entry_2 = Entry(root)
entry_2.place(x=240,y=180)
label_3 = Label(root, text="Phone no.",width=20,font=("bold", 10))
label_3.place(x=70,y=180)

entry_3 = Entry(root)
entry_3.place(x=240,y=130)


label_4 = Label(root, text="State",width=20,font=("bold", 10))
label_4.place(x=70,y=280)

label_5 = Label(root, text="set password",width=20,font=("bold", 10))
label_5.place(x=100,y=150)

entry_5 = Entry(root)
entry_5.place(x=260,y=155)

label_1 = Label(root, text="FullName",width=20,font=("bold", 10))
label_1.place(x=80,y=130)

list1 = ['Maharashra','kolkata','delhi','up','MP','Punjab'];
c=StringVar()
droplist=OptionMenu(root,c, *list1)
droplist.config(width=15)
c.set('select your State') 
droplist.place(x=240,y=280)






entry_5 = Entry(root)
entry_5.place(x=240,y=130)
Button(root, text='Submit',width=20,bg='brown',fg='white').place(x=180,y=380)

root.mainloop()

```


```python
from tkinter import *
from tkinter import messagebox

 
def Ok():
    uname = e1.get()
    password = e2.get()
 
    if(uname == "" and password == "") :
        messagebox.showinfo("", "Blank Not allowed")
 
 
    elif(uname == "Admin" and password == "123"):
 
        messagebox.showinfo("","Login Success")
        root.destroy()
 
    else :
        messagebox.showinfo("","Incorrent Username and Password")
 
 
root = Tk()
root.title("Login")
root.geometry("300x200")
global e1
global e2
 
Label(root, text="FullName").place(x=10, y=10)
Label(root, text="Password").place(x=10, y=40)
 
e1 = Entry(root)
e1.place(x=140, y=10)
 
e2 = Entry(root)
e2.place(x=140, y=40)
e2.config(show="*")
 
 
Button(root, text="Login", command=Ok ,height = 3, width = 13).place(x=10, y=100)
 
root.mainloop()
```


```python
from tkinter import *

def createListinListBox(shopping):
    for elem in shopping:
        theList.insert(END,elem[0] + "-" + str(elem[1]))

def listIndex(shopping, item):
    index = -1
    for i in range(len(shopping)):
        if shopping[i][0] == item:
            index = i
    return index

def addList(shopping, item, index):
    if index == -1:
        shopping.append([item,1])
    else:
        shopping[index][1] += quantity.get()

def removeList(sopping, index):
    del(shopping[index])

def add():
    index = listIndex(shopping, item.get())
    addList(shopping, item.get(), index)
    if index >=0:
        theList.delete(index)
        theList.insert(index,shopping[index][0] + "-" + str(shopping[index][1]))
    else:
        theList.insert(END,item.get() + "-" + str(quantity.get()))

def remove():
    index = theList.index(ACTIVE)
    print(index)
    removeList(shopping, index)
    theList.delete(index)

shopping = [["Cashews/packet" ,0],["Almonds/packet", 0], ["Pistachios/packet", 0], ["Apricots/Packet", 0], ["Raisins/packet", 0]]

window = Tk()
window.title("Shopping List")

theList = Listbox(window, selectmode=SINGLE)
theList.grid(row=0,column=0,columnspan=2,sticky=E)

createListinListBox(shopping)

item=StringVar()
quantity=IntVar()

quantity.set(1)

Label(window, text="Item:").grid(row=1, column=0, sticky=E)
Entry(window, textvariable=item).grid(row=1, column=1, sticky=W)

Label(window, text="Quantity:").grid(row=2, column=0, sticky=E)
Entry(window, textvariable=quantity).grid(row=2, column=1, sticky=W)

Button(window, text="Add", command=add).grid(row=3, column=0, columnspan=3)
Button(window, text="Remove", command=remove).grid(row=0, column=3)

window.mainloop()

```

    0
    


```python

```
