# PDF Splitter

This is a simple Python script just for excercise that splits a PDF file into smaller PDF files, each containing a specified number of pages. The script uses the PyPDF2 and tkinter libraries.

## Required Libraries

- os
- PyPDF2
- tkinter

## Functions

### `divide_pdf(input_pdf, output_directory, pages_per_file)`

This function takes an input PDF file, an output directory, and the number of pages per smaller PDF file as arguments. It reads the input PDF file and creates smaller PDF files with the specified number of pages. The new files are saved in the output directory. The function returns `True` if the splitting process is successful, otherwise, it returns `False` and displays an error message.

### `select_input_file()`

This function opens a file dialog for the user to select the input PDF file to be split. It returns the file path of the selected file.

### `select_output_directory()`

This function opens a directory dialog for the user to select the output directory where the smaller PDF files will be saved. It returns the folder path of the selected directory.

### `ask_pages_per_file()`

This function prompts the user to enter the number of pages per smaller PDF file. It returns the integer value entered by the user.

### `ask_continue()`

This function asks the user if they want to split another file. It returns `True` if the user wants to continue, otherwise, it returns `False`.

## Main Loop

The script uses a `while` loop to continuously prompt the user for input and process the PDF files until the user chooses to exit. The user is asked to select an input PDF file, an output directory, and the number of pages per smaller PDF file. If any of these inputs are not provided, the script exits. The `divide_pdf()` function is called to split the PDF file, and a success message is displayed if the splitting process is successful. The user is then asked if they want to split another file or exit the program.

## How to Run the Script

1. Ensure you have Python installed on your system. This script was written using Python 3.

2. Install the required libraries by running the following command in your terminal or command prompt:

3. Save the script in a file named `pdf_splitter.py`.

4. Run the script by executing the following command in your terminal or command prompt:

5. Follow the prompts to select the input PDF file, output directory, and the number of pages per smaller PDF file.

6. The script will create smaller PDF files in the output directory, and you'll be prompted to split another file or exit the program.

## Limitations and Future Improvements

- The script does not support splitting a PDF file based on a custom range of pages. This feature can be added to offer more flexibility to users.

- Error handling can be improved to provide more detailed information and solutions to the user when an issue occurs.
