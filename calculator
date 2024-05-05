import tkinter as tk
import winsound



def click_button(text_button):

    current_text = entry.get()

    if text_button == "=":
        try: 
            result = eval(current_text)
            #delete the input textA
            entry.delete(0,tk.END)
            #enter the result 
            entry.insert(tk.END, str(result))
        except:
            #if error encountered inform the user 
            entry.delete(0, tk.END)
            entry.insert(tk.END, "Error!")
    elif text_button == "C":
        entry.delete(0, tk.END)
    else:
        entry.insert(tk.END, text_button)

    #use both the filename and aysnc to allow the sound to play in background
    #and avoid lag
    
    winsound.PlaySound("click.wav", winsound.SND_FILENAME | winsound.SND_ASYNC)
    


#create the main window 
root = tk.Tk()
root.title("Calculator")

#the widget 
entry = tk.Entry(root, width=20, font=("Georgia",20), bd=5, relief=tk.GROOVE, bg="lightgray", fg="black")
entry.grid(row=0,column=0,columnspan=4,padx=30,pady=30)

#defining buttons 
buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*', 
    '1', '2', '3', '-',
    '0', 'C', '=', '+'
]
row_val = 1
col_val = 0

for button_text in buttons:
    if button_text[0] == "=":
        button = tk.Button(root,text=button_text[0], width=5, height=2, font=("Georgia",14), bg = "#ADD8E6", command=lambda b=button_text[0]:click_button(b))
    elif button_text[0] == "C":
        button = tk.Button(root,text=button_text[0], width=5, height=2, font=("Georgia",14), bg = "#FF6347", command=lambda b=button_text[0]:click_button(b))
    else:
        button = tk.Button(root,text=button_text[0], width=5, height=2, font=("Georgia",14), bg = "#E6E6FA", command=lambda b=button_text[0]:click_button(b))
    #tk.Button(root,text=button, width=5, height=2, font=("Georgia",14), command=lambda b=button:click_button(b)).grid(row= row_val ,column=col_val,padx=5,pady=5)
    button.grid(row= row_val ,column=col_val,padx=5,pady=5)
    col_val += 1
    if col_val >3:
        col_val = 0
        row_val += 1

root.mainloop()

