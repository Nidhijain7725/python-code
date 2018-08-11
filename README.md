# python-code
import pymysql
db = pymysql.connect("localhost", "root", "", "ST_CPYTHON")
cursor = db.cursor()

from tkinter import*
from tkinter.ttk import*

root=Tk()
root.title("Movies List")
root.geometry("800x500")


tree=Treeview(root)
tree["column"]=("Movie_ID","Movie_Name","Genre","Actor")

tree.column("Movie_ID",width=140)
tree.column("Movie_Name",width=140)
tree.column("Genre",width=140)
tree.column("Actor",width=140)

tree.heading("Movie_ID",text="Movie_ID")
tree.heading("Movie_Name",text="Movie_Name")
tree.heading("Genre",text="Genre")
tree.heading("Actor",text="Actor")

tree.place(x=10,y=150)

def callback(n):
  x = tree.get_children()
  for item in x:
       tree.delete(item)
  i=0
  cursor.execute("select * from Movie where Movie_Name like %s ORDER BY Movie_Name ASC",(n+"%"))
  rows = cursor.fetchall()

  for r in rows:
    Movie_ID = r[0]
    Movie_Name = r[1]
    Genre = r[2]
    Actor = r[3]
    tree.insert("", i, text=i + 1, values=(r[0], r[1], r[2], r[3]))
    i += 1
b1=Button(root,text="A",width=2,command=lambda:callback("a"))
b1.grid(row=0,column=0)


b2=Button(root,text="B",width=2,command=lambda:callback("b"))
b2.grid(row=0,column=1)


b3=Button(root,text="C",width=2,command=lambda:callback("c"))
b3.grid(row=0,column=2)

b4=Button(root,text="D",width=2,command=lambda:callback("d"))
b4.grid(row=0,column=3)

b5=Button(root,text="E",width=2,command=lambda:callback("e"))
b5.grid(row=0,column=4)

b6=Button(root,text="F",width=2,command=lambda:callback("f"))
b6.grid(row=0,column=5)

b7=Button(root,text="G",width=2,command=lambda:callback("g"))
b7.grid(row=0,column=6)

b8=Button(root,text="H",width=2,command=lambda:callback("h"))
b8.grid(row=0,column=7)

b9=Button(root,text="I",width=2,command=lambda:callback("i"))
b9.grid(row=0,column=8)

b10=Button(root,text="J",width=2,command=lambda:callback("j"))
b10.grid(row=0,column=9)

b11=Button(root,text="K",width=2,command=lambda:callback("k"))
b11.grid(row=0,column=10)

b12=Button(root,text="L",width=2,command=lambda:callback("l"))
b12.grid(row=0,column=11)

b13=Button(root,text="M",width=2,command=lambda:callback("m"))
b13.grid(row=0,column=12)

b14=Button(root,text="N",width=2,command=lambda:callback("n"))
b14.grid(row=0,column=13)

b15=Button(root,text="O",width=2,command=lambda:callback("o"))
b15.grid(row=0,column=14)

b16=Button(root,text="P",width=2,command=lambda:callback("p"))
b16.grid(row=0,column=15)

b17=Button(root,text="Q",width=2,command=lambda:callback("q"))
b17.grid(row=0,column=16)

b18=Button(root,text="R",width=2,command=lambda:callback("r"))
b18.grid(row=0,column=17)

b19=Button(root,text="S",width=2,command=lambda:callback("s"))
b19.grid(row=0,column=18)

b20=Button(root,text="T",width=2,command=lambda:callback("t"))
b20.grid(row=0,column=19)

b21=Button(root,text="U",width=2,command=lambda:callback("u"))
b21.grid(row=0,column=20)

b22=Button(root,text="V",width=2,command=lambda:callback("v"))
b22.grid(row=0,column=21)

b23=Button(root,text="W",width=2,command=lambda:callback("w"))
b23.grid(row=0,column=22)

b24=Button(root,text="X",width=2,command=lambda:callback("x"))
b24.grid(row=0,column=23)

b25=Button(root,text="Y",width=2,command=lambda:callback("y"))
b25.grid(row=0,column=24)

b26=Button(root,text="Z",width=2,command=lambda:callback("z"))
b26.grid(row=0,column=25)

root.mainloop()
db.close()
