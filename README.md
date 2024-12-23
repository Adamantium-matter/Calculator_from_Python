# Calculator Application

This repository contains a simple calculator application built using the Python `Tkinter` library. The project demonstrates how to create a functional and interactive desktop GUI application.

## Features

- **Basic Calculator Operations**: Perform addition, subtraction, multiplication, and division.
- **User-Friendly Interface**: Clear and intuitive layout.
- **Interactive Buttons**: Buttons for numbers, operations, and special functions like clear (C) and evaluate (=).
- **Cross-Platform**: Runs on Windows, macOS, and Linux.

## Requirements

- Python 3.x
- No external libraries are required as `Tkinter` is included in Python's standard library.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/CYPERSWAMI/Calculator_from_Python.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Calculator_from_python
   ```

3. Run the application:
   ```bash
   python calculator.py
   ```

## Usage

- Launch the application by running the script.
- Click the buttons to input numbers and operations.
- Use the `=` button to evaluate the expression.
- Use the `C` button to clear the input.

## Code Overview

### Main Components:

- **Main Window**: The root window created using `Tk`.
- **Entry Widget**: Displays the current input and results.
- **Buttons**: Numeric and operation buttons are placed using absolute positioning for a calculator layout.
- **Event Handling**: Buttons use `command` to trigger functions for updating the display, clearing input, or evaluating expressions.

### Code:
Here is the main code for the application:

```python
from tkinter import Tk, Entry, Button, StringVar

class Calculator:
    def __init__(self, master):
        master.title("Calculator")
        master.geometry('357x420+0+0')
        master.config(bg='black')
        master.resizable(False, False)

        self.equation = StringVar()
        self.entry_value = ''
        Entry(width=17, bg='#D3D3D3', font=('Arial Bold', 28), textvariable=self.equation).place(x=0, y=0)

        Button(width=11, height=4, text='(', relief='flat', bg='black', fg='white', command=lambda: self.show('(')).place(x=0, y=50)
        Button(width=11, height=4, text=')', relief='flat', bg='black', fg='white', command=lambda: self.show(')')).place(x=90, y=50)
        Button(width=11, height=4, text='%', relief='flat', bg='black', fg='white', command=lambda: self.show('%')).place(x=180, y=50)
        Button(width=11, height=4, text='1', relief='flat', bg='blue', fg='white', command=lambda: self.show(1)).place(x=0, y=125)
        Button(width=11, height=4, text='2', relief='flat', bg='blue', fg='white', command=lambda: self.show(2)).place(x=90, y=125)
        Button(width=11, height=4, text='3', relief='flat', bg='blue', fg='white', command=lambda: self.show(3)).place(x=180, y=125)
        Button(width=11, height=4, text='4', relief='flat', bg='blue', fg='white', command=lambda: self.show(4)).place(x=0, y=200)
        Button(width=11, height=4, text='5', relief='flat', bg='blue', fg='white', command=lambda: self.show(5)).place(x=90, y=200)
        Button(width=11, height=4, text='6', relief='flat', bg='blue', fg='white', command=lambda: self.show(6)).place(x=180, y=200)
        Button(width=11, height=4, text='7', relief='flat', bg='blue', fg='white', command=lambda: self.show(7)).place(x=0, y=275)
        Button(width=11, height=4, text='8', relief='flat', bg='blue', fg='white', command=lambda: self.show(8)).place(x=180, y=275)
        Button(width=11, height=4, text='9', relief='flat', bg='blue', fg='white', command=lambda: self.show(9)).place(x=90, y=275)
        Button(width=11, height=4, text='0', relief='flat', bg='blue', fg='white', command=lambda: self.show(0)).place(x=90, y=350)
        Button(width=11, height=4, text='.', relief='flat', bg='black', fg='white', command=lambda: self.show('.')).place(x=270, y=350)
        Button(width=11, height=4, text='+', relief='flat', bg='black', fg='white', command=lambda: self.show('+')).place(x=270, y=275)
        Button(width=11, height=4, text='-', relief='flat', bg='black', fg='white', command=lambda: self.show('-')).place(x=270, y=200)
        Button(width=11, height=4, text='/', relief='flat', bg='black', fg='white', command=lambda: self.show('/')).place(x=270, y=50)
        Button(width=11, height=4, text='X', relief='flat', bg='black', fg='white', command=lambda: self.show('*')).place(x=270, y=125)
        Button(width=11, height=4, text='=', relief='flat', bg='black', fg='white', command=self.solve).place(x=180, y=350)
        Button(width=11, height=4, text='C', relief='flat', bg='red', fg='black', command=self.clear).place(x=0, y=350)

    def show(self, value):
        self.entry_value += str(value)
        self.equation.set(self.entry_value)

    def clear(self):
        self.entry_value = ''
        self.equation.set(self.entry_value)

    def solve(self):
        result = eval(self.entry_value)
        self.equation.set(result)

root = Tk()
calculator = Calculator(root)
root.mainloop()
```

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request if you have ideas for improving this project.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments

- Python documentation: [Tkinter](https://docs.python.org/3/library/tkinter.html)
- Inspiration from the Python community.

---

Enjoy using this calculator application!

