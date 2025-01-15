import tkinter

window = tkinter.Tk()
window.title("BMI Checker")
window.minsize(width=350, height=200)
window.configure(bg='brown')



def click_button():

    try:
        kilo_bilgisi = float(kilo_entry.get())
        boy_bilgisi = float(boy_entry.get())
        bim = kilo_bilgisi / (boy_bilgisi**2)

        if bim < 18.4:
            category="Zayıf"
        if 18.5 < bim < 24.9:
            category="Normal"
        if 25 < bim < 39.9:
            category="Normalden Kilolu"
        if 40 <= bim:
            category="Obez"

        result_label.config(text=f"{category}")
    except:
        result_label.config(text="Lütfen yalnızca sayı giriniz.")
        print("can")




my_label = tkinter.Label(text="Vücut Kitle İndeksi Hesaplayıcı", font=('Arial', 15,"bold"))
my_label.config(bg="white",fg="blue")
my_label.pack()

boy_label = tkinter.Label(text="Boyunuz (metre)",font=('Arial', 12, "bold"))
boy_label.config(bg="grey",fg="white")
boy_label.pack()

boy_entry = tkinter.Entry(width=15,bg="white",fg="black")

boy_entry.pack()


kilo_label = tkinter.Label(text="Kilonuz (kg)",font=('Arial', 12, "bold"))
kilo_label.config(bg="grey",fg="white")
kilo_label.pack()


kilo_entry = tkinter.Entry(width=20,bg="white",fg="black")
kilo_entry.pack()

my_button = tkinter.Button(text="Hesapla", command=click_button)
my_button.config(bg="gray",fg="black")
my_button.pack(side="top")

result_label = tkinter.Label(text=" ",font=('Arial', 12, "bold"))
result_label.pack()


window.mainloop()

