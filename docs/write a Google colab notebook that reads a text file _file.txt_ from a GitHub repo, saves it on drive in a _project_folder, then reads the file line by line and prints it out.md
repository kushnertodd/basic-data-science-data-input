To read a file from GitHub, save it to Google Drive, and print it line by line, run this code in a [Google Colab](https://colab.research.google.com/) notebook.

## **Code**

*`# 1. Connect your Google Drive`*  
`from google.colab import drive`  
`import os`  
`import requests`

`drive.mount('/content/drive')`

*`# 2. Create the "project" folder in Google Drive if it does not exist`*  
`folder_path = '/content/drive/My Drive/project'`  
`os.makedirs(folder_path, exist_ok=True)`

*`# 3. Download the text file from GitHub`*  
*`# Replace the URL below with your raw GitHub file link`*  
`github_url = 'https://githubusercontent.com'`

`response = requests.get(github_url)`  
`response.raise_for_status()  # Check if the download was successful`

*`# 4. Save the file locally in the Google Drive "project" folder`*  
`file_path = os.path.join(folder_path, 'file.txt')`  
`with open(file_path, 'w', encoding='utf-8') as f:`  
    `f.write(response.text)`

*`# 5. Read the saved file line by line and print it out`*  
`print('Reading file from Google Drive:\n')`  
`with open(file_path, 'r', encoding='utf-8') as f:`  
    `for line in f:`  
        `print(line, end='')`

## **Steps to Use**

> 1. Open a new notebook in Google Colab.  
> 2. Paste the code into a code cell.  
> 3. Replace 'https://githubusercontent.com' with the actual **Raw** URL of your file on GitHub.  
> 4. Run the cell and follow the prompt to allow access to your Google Drive.

Would you like me to show you how to **handle large files** line by line without loading the whole file into memory at once, or how to **handle errors** if the GitHub link is invalid?