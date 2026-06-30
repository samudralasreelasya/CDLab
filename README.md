# CDLab
# CD Lab (Compiler Design Laboratory)

This repository contains the laboratory assignments and source code for the Compiler Design course. The environment is configured using GitHub Codespaces to implement and test lexical analysers and parsers.

## 🚀 Getting Started & Environment Setup

This project was built from scratch using the following step-by-step setup process:

1. **Repository Creation:** Created this `CDLab` repository on GitHub with an initial `README.md` file.
2. **Development Environment:** Launched and opened the project inside **GitHub Codespaces**.
3. **Tool Installation:** Installed the necessary compilation tools directly from the terminal using the package manager:
   ```bash
   sudo apt update
   sudo apt install gcc bison flex -y
   ```

---

## 📁 Project Structure

* `lex.l` - The Lex/Flex source file containing token definitions and regular expressions.
* `README.md` - Documentation of the project setup and execution workflow.

---

## 🛠️ Execution Process

To run the lexical analyser (`lex.l`) inside your terminal, follow these steps in order:

### Step 1: Generate the C Code
Run the `flex` command on your source file. This generates a lexical analyser source file named `lex.yy.c`.
```bash
flex lex.l
```

### Step 2: Compile the Generated C File
Use `gcc` to compile the generated `lex.yy.c` file. Use the `-o` flag to name your executable output file (e.g., `lex`).
```bash
gcc lex.yy.c -o lex
```
*(Note: If your code uses standard Flex libraries and throws an error, you can append the library flag: `gcc lex.yy.c -o lex -lfl`)*

### Step 3: Run the Executable
Execute the compiled binary file to start testing your lexical analyser:
```bash
./lex
```

---

## 📝 Technical Details of the Process

* **Flex (Fast Lexical Analyzer Generator):** Reads the user-defined rules in `lex.l` and converts them into a highly optimised C program (`lex.yy.c`).
* **GCC (GNU Compiler Collection):** Compiles the raw C code into machine-readable binary code.
* **Input/Output:** Once you run `./lex`, the program waits for user input in the terminal. It will scan your text and output the tokens based on the rules specified in your `lex.l` file. Press `Ctrl + D` to send an End-Of-File (EOF) signal and exit the running program.
