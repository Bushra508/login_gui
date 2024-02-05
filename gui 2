import tkinter as tk
from tkinter import messagebox
import mysql.connector as ms
m=ms.connect(host="localhost", user='root', password='&Bushra.S.583', database='login_info')
cursor=m.cursor()

def login():
    email = email_entry.get()
    password = password_entry.get()
    value=(email,)
    sql="select * from auth where id = %s"
    cursor.execute(sql,value)
    L = cursor.fetchall()
    if len(L)==0:
        messagebox.showinfo("ERROR","ID not found")
    
    else:
        value=(email,password)
        sql="select * from auth where id = %s and password = %s"
        cursor.execute(sql,value)
        L = cursor.fetchall()
        if len(L)==0:
            messagebox.showinfo("ERROR","Not the correct password")
        else:
            messagebox.showinfo("LOGGED IN","Successfully logged in!")
    
    
root = tk.Tk()
root.title("Authorisation Window")   #window ka name

# Create labels and entry fields for email and password
email_label = tk.Label(root, text="Email")
email_label.pack()
email_entry = tk.Entry(root)
email_entry.pack()

password_label = tk.Label(root, text="Password")
password_label.pack()
password_entry = tk.Entry(root, show="*")  # 'show' option hides the entered password
password_entry.pack()

# Create a login button to trigger the login function
login_button = tk.Button(root, text="Login", command=login)
login_button.pack()


# Start the main loop
root.mainloop()
m.commit()
cursor.close()
m.close()
