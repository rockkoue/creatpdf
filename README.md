# creatpdf
upload some image file and generate en pdf doc with python language
import tkinter as tk
from PIL import Image
from tkinter import filedialog
from tkinter.ttk import *

root = tk.Tk()

root.call('wm', 'attributes', '.', '-topmost', True)
def open_file(): 
    files = filedialog.askopenfilename(multiple=True) 
    var = root.tk.splitlist(files)
    filePaths = []
    for f in var:
        filePaths.append(f)
    filePaths
    Table=[]
    for i in range(len( filePaths)):
        Table.append(Image.open( filePaths[i]))
    Table[0].save('phopdfs.pdf','PDF',resolution=100.0,save_all=1,append_images=Table)
button =tk.Button(root,text="open file",command=open_file)
button.pack()
root.mainloop()
