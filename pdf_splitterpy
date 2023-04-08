import os
import PyPDF2
import tkinter as tk
from tkinter import filedialog, messagebox, simpledialog

def divide_pdf(input_pdf, output_directory, pages_per_file):
    try:
        with open(input_pdf, 'rb') as file:
            reader = PyPDF2.PdfReader(file)

            # Controlla il numero di pagine nel PDF
            num_pages = len(reader.pages)

            # Loop attraverso tutte le pagine e creare nuovi file PDF
            for i in range(0, num_pages, pages_per_file):
                output_pdf = os.path.join(output_directory, f'output_{i // pages_per_file + 1}.pdf')
                writer = PyPDF2.PdfWriter()

                for j in range(i, min(i + pages_per_file, num_pages)):
                    writer.add_page(reader.pages[j])

                with open(output_pdf, 'wb') as output_file:
                    writer.write(output_file)
            return True
    except Exception as e:
        messagebox.showerror("Errore", f"Si è verificato un errore durante la divisione del file PDF: {e}")
        return False

def select_input_file():
    root = tk.Tk()
    root.withdraw()
    messagebox.showinfo("Selezione file", "Scegli il file da dividere")
    file_path = filedialog.askopenfilename(filetypes=[("PDF files", "*.pdf")])
    return file_path

def select_output_directory():
    root = tk.Tk()
    root.withdraw()
    messagebox.showinfo("Selezione cartella", "Scegli la cartella dove salvare i file divisi")
    folder_path = filedialog.askdirectory()
    return folder_path

def ask_pages_per_file():
    root = tk.Tk()
    root.withdraw()
    num_pages = simpledialog.askinteger("Numero di pagine", "Inserisci il numero di pagine per ciascun nuovo file PDF:", minvalue=1)
    return num_pages

def ask_continue():
    root = tk.Tk()
    root.withdraw()
    return messagebox.askyesno("Continuare?", "Vuoi dividere un altro file?")

while True:
    # Chiede all'utente i parametri del programma
    input_pdf = select_input_file()
    if not input_pdf:
        messagebox.showinfo("Chiusura!", "Il programma verrà chiuso.")
        break


    output_directory = select_output_directory()
    if not output_directory:
        messagebox.showinfo("Chiusura!", "Il programma verrà chiuso.")
        break


    pages_per_file = ask_pages_per_file()
    if not pages_per_file:
        messagebox.showinfo("Chiusura!", "Il programma verrà chiuso.")
        break


    # Esegui la funzione per dividere il PDF
    success = divide_pdf(input_pdf, output_directory, pages_per_file)
    messagebox.showinfo("Successo!", f"Il file è stato diviso con successo, è stato salvato nella cartella scelta: {output_directory}")

    # Se la divisione è andata a buon fine, chiede all'utente se si desidera dividere altri file
    if success:
        if not ask_continue():
            messagebox.showinfo("Chiusura!", "Il programma verrà chiuso.")
            break

    else:
        # Se si è verificato un errore, chiede all'utente se si desidera riprovare
        retry = messagebox.askyesno("Riprova", "Vuoi riprovare con un altro file?")
        if not retry:
            messagebox.showinfo("Chiusura!", "Il programma verrà chiuso.")
            break





