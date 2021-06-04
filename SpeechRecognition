import speech_recognition as sr
import pyttsx3
import tkinter as tk
import webbrowser
import wikipedia
engine=pyttsx3.init()

greetings=["hello","hi","hey","wassup"]
wish={"morning":"Good morning","night":"Good night","care":"you too","bye":"please don't go","best people":"sri soorya akshat"}
silly={"marry":"no i have a boy friend","love":"i love myself","hate":"lamao look at your face","children":"oh please."}

def check():
    r=sr.Recognizer()
    with microphone() as source:
        audio=r.listen(source)
        order=r.recognize_google(audio,language="en=in")
        e2.insert(ek.End,order)
        x=order.split(" ")
        
        for word in x:
            if word in greetings:
                answer="Hey my name is jarvis; how may i help you"
            elif word in wish:
                answer=wish[word]
                engine.say(answer)
                engine.runAndWait()
                e1.insert(tk.END,answer)
            elif "play" in x:
                webbrowser.open_new(f"https://www.youtube.com/result?search_querry={x[1]}")
            elif "search"in x:
                webbrowser.open_new(f"https://www.google.com/search?q={x[1]}")
            elif word in silly:
                answer=silly[word]
                engine.say(answer)
                engine.runAndWait()
                e1.insert(tk.END,answer)
            elif "quit" in x:
                root.destroy()
                

                
root=tk.Tk()
root.geometry("400x400")
root.title('speech recognition')
root.configure(bg="black")
e1=tk.Text(root)
e1.place(x=10,y=35,height=50,width=180)
l1=tk.Label(root,text="Output:")
l1.place(x=10,y=5)
e2=tk.Text(root)
e2.place(x=10,y=150,height=30,width=180)
l2=tk.Label(text="Input:")
l2.place(x=10,y=120)
b=tk.Button(root,text="SPEAK",bg="green",fg="white",command=check)
b.place(x=50,y=200,height=50,width=100)
root.mainloop()
