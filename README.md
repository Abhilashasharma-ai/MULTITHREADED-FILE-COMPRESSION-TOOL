# MULTITHREADED-FILE-COMPRESSION-TOOL
COMPANY NAME: CODETECH IT SOLUTION

NAME: ABHILASHA SHARMA

INTERN ID: CT04DF338

DOMAIN: C++

MENTOR: NEELA SANTOSH

#DISCRIPTION:
The given C++ program is a console-based tool that demonstrates the concept of **Run-Length Encoding (RLE)**, a simple yet effective form of **lossless data compression**. The tool allows users to either **compress** or **decompress** a file using the RLE algorithm. The program is modular, with clear function definitions for both compression and decompression, and it guides the user through file-based input and output operations. In this essay, we will explore the program's structure, functionality, and logic in detail, highlighting how each part contributes to the overall workflow.

---

### **Understanding RLE (Run-Length Encoding)**

Run-Length Encoding is a straightforward technique where sequences of the same character are stored as a single character followed by the number of times it appears consecutively. For example, the string `aaabb` would be compressed to `a3b2`. It is useful in scenarios where characters repeat often, such as in simple graphic files or repetitive text data.

---

### **Structure of the Program**

The program includes several important C++ headers:

* `<iostream>` for input/output operations,
* `<fstream>` for file handling,
* `<string>` for string manipulation, and
* `<cctype>` for checking character types such as digits.

The program defines two main functions: `compressRLE()` and `decompressRLE()`, along with the `main()` function which controls the flow and handles user interaction and file operations.

---

### **RLE Compression: `compressRLE` Function**

The `compressRLE` function receives a string and compresses it using RLE. It initializes a `count` variable to 1 and iterates through the string starting from the second character (index 1). For each character, it checks if it is the same as the previous one. If it is, it increases the count. If not, it appends the previous character and its count to the result string and resets the count to 1. This process continues until all characters have been processed. The final compressed string is then returned.

This function is efficient for strings with consecutive repeating characters. For instance, input `aaaabbc` becomes `a4b2c1`, reducing storage if the string contains many repeated elements.

---

### **RLE Decompression: `decompressRLE` Function**

The `decompressRLE` function does the reverse of compression. It reads the input character-by-character and assumes each character is followed by a number indicating how many times it appears. It stores digits following a character in a string until a non-digit is encountered. Then, it converts the string of digits to an integer using `stoi()` and appends the character that many times to the result string using `result.append(count, character)`. This loop continues until the entire string is decoded.

For example, if the input is `a4b2c1`, it reconstructs the original string `aaaabbc`.

---

### **Main Function: User Interaction and File Handling**

The `main()` function begins by prompting the user to choose between compression and decompression. It then asks for the input file and output file names. These are stored in `inputFile` and `outputFile`.

The program opens the input file using an `ifstream` object and reads its entire content into a string using `istreambuf_iterator`, which reads the file character-by-character efficiently. Once the data is read, the file is closed.

Based on the user’s choice, either `compressRLE()` or `decompressRLE()` is called, and the result is stored in the `output` string. The program then opens the output file using `ofstream` and writes the processed string to it. After writing, it closes the file and prints a message indicating successful completion of the operation.

---

### **Error Handling and Robustness**

The program includes basic error handling: it checks whether the input and output files can be opened and provides appropriate error messages using `cerr`. It also handles invalid user input gracefully by validating the choice entered.

---

### **Conclusion**

This program is a well-structured example of how compression algorithms can be implemented in C++ using simple logic and file operations. It effectively demonstrates both **RLE compression** and **decompression**, making it a practical introduction to data encoding. By integrating user interaction, file handling, and string manipulation, the code not only compresses and decompresses data but also emphasizes the importance of modular design, error checking, and efficient algorithmic thinking in programming.

OUTPUT:
![Image](https://github.com/user-attachments/assets/0bbcb5d1-0b74-488b-9bef-ba160b7c35cc)

![Image](https://github.com/user-attachments/assets/78f03c6b-7acf-4e63-ae8d-a3a95b04c466)

![Image](https://github.com/user-attachments/assets/5ea94621-db78-4a28-bfe1-ffe2d4e73c4d)
