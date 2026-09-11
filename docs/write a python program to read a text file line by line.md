The most efficient and Pythonic way to **read a text file line by line** is by iterating directly over the file object using a for loop combined with a with statement. \[1, 2\]

Using the with statement is best practice because it **automatically closes the file** once the block finishes executing, even if an error occurs. Iterating over the file object directly ensures that only one line is loaded into memory at a time, making it highly memory-efficient for large files. \[1, 3, 4\]

## **Python Program**

*`# Define the path to your text file`*  
`file_path = "example.txt"`

`try:`  
    `# Open the file in read mode ('r')`  
    `with open(file_path, "r", encoding="utf-8") as file:`  
        `# Iterate over each line in the file object`  
        `for line in file:`  
            `# strip() removes the trailing newline character (\n) and whitespace`  
            `clean_line = line.strip()`  
              
            `# Print the line`  
            `print(clean_line)`

`except FileNotFoundError:`  
    `print(f"Error: The file at {file_path} was not found.")`  
`except IOError:`  
    `print("Error: An I/O error occurred while handling the file.")`

## **Why use .strip()?**

Each line read from a text file naturally retains its trailing newline character (\\n). Because Python's built-in print() function automatically adds its own newline, leaving the character intact results in unwanted blank lines between your output. Applying .strip() prevents this by cleaning up the trailing whitespace. \[1, 3, 5, 6\]

---

If you would like to expand on this, let me know if you need to:

> * **Search for specific keywords** or patterns within the lines.  
> * Track line counts using the **enumerate() function**.  
> * Write the modified lines into a **new output file**. \[7\]

\[1\] [https://www.geeksforgeeks.org](https://www.geeksforgeeks.org/python/read-a-file-line-by-line-in-python/)  
\[2\] [https://www.freecodecamp.org](https://www.freecodecamp.org/news/how-to-read-a-file-line-by-line-in-python/)  
\[3\] [https://www.youtube.com](https://www.youtube.com/watch?v=t33mP648uIc)  
\[4\] [https://www.geeksforgeeks.org](https://www.geeksforgeeks.org/python/how-to-read-from-a-file-in-python/)  
\[5\] [https://www.youtube.com](https://www.youtube.com/watch?v=arscRaN29bM&t=1)  
\[6\] [https://docs.python.org](https://docs.python.org/3/tutorial/inputoutput.html)  
\[7\] [https://pynative.com](https://pynative.com/python-read-specific-lines-from-a-file/)