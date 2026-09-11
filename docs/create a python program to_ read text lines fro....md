

Python

def sort\_text\_file(input\_filepath, output\_filepath):  
    """  
    Reads text lines from an input file, sorts them alphabetically,  
    and writes the sorted lines to an output file.

    Args:  
        input\_filepath (str): The path to the input text file.  
        output\_filepath (str): The path to the output text file.  
    """  
    try:  
        with open(input\_filepath, 'r') as infile:  
            lines \= infile.readlines()  
    except FileNotFoundError:  
        print(f"Error: Input file not found at '{input\_filepath}'")  
        return

    sorted\_lines \= sorted(lines)

    try:  
        with open(output\_filepath, 'w') as outfile:  
            outfile.writelines(sorted\_lines)  
        print(f"Successfully read, sorted, and wrote lines to '{output\_filepath}'")  
    except Exception as e:  
        print(f"Error writing to output file '{output\_filepath}': {e}")

if \_\_name\_\_ \== "\_\_main\_\_":  
    input\_file \= r"C:\\Users\\kushn\\projects\\sort\\input.txt"  
    output\_file \= r"C:\\Users\\kushn\\projects\\sort\\output.txt"  
    sort\_text\_file(input\_file, output\_file)

**Explanation:**

1. **sort\_text\_file(input\_filepath, output\_filepath) function:**  
   * Takes the input and output file paths as arguments.  
   * **Reading from the input file:**  
     * try...except FileNotFoundError: This block handles the case where the input file doesn't exist.  
     * with open(input\_filepath, 'r') as infile:: Opens the input file in read mode ('r'). The with statement ensures that the file is automatically closed even if errors occur.  
     * lines \= infile.readlines(): Reads all lines from the input file and stores them as a list of strings in the lines variable. Each string in the list will include the newline character (\\n) at the end of the line (except for the last line if it doesn't have one).  
   * **Sorting the lines:**  
     * sorted\_lines \= sorted(lines): The built-in sorted() function takes the lines list as input and returns a new list containing all items from the original list in ascending order (alphabetically for strings).  
   * **Writing to the output file:**  
     * try...except Exception as e: This block handles potential errors during the writing process.  
     * with open(output\_filepath, 'w') as outfile:: Opens the output file in write mode ('w'). If the file exists, its contents will be overwritten. If it doesn't exist, it will be created.  
     * outfile.writelines(sorted\_lines): Writes all the strings in the sorted\_lines list to the output file. writelines() writes each string in the list without adding any additional newline characters. Since the lines read from the input file already had newline characters, the output file will also have each line on a new line.  
     * print(...): Prints a success message to the console.  
   * except Exception as e:: Catches any other potential errors during file writing and prints an error message.  
2. **if \_\_name\_\_ \== "\_\_main\_\_": block:**  
   * This ensures that the code inside this block only runs when the script is executed directly (not when it's imported as a module).  
   * input\_file \= r"C:\\Users\\kushn\\projects\\sort\\input.txt": Defines the path to the input file. The r before the string indicates a raw string, which is useful for Windows paths as it prevents backslashes from being interpreted as escape sequences.  
   * output\_file \= r"C:\\Users\\kushn\\projects\\sort\\output.txt": Defines the path to the output file.  
   * sort\_text\_file(input\_file, output\_file): Calls the sort\_text\_file function with the specified input and output file paths to perform the sorting operation.

**How to Run the Python Program:**

1. **Save:** Save the code in a file named sort\_lines.py (or any other .py extension).  
2. **Create Input File:** Make sure you have a file named input.txt at the location C:\\Users\\kushn\\projects\\sort\\ with the text lines you want to sort (each line on a new line).  
3. **Open Terminal or Command Prompt:** Navigate to the directory where you saved the sort\_lines.py file.  
4. **Run:** Execute the Python script using the python command:  
   Bash  
   python sort\_lines.py

After running the script, the sorted lines from input.txt will be written to a new file named output.txt in the same directory.