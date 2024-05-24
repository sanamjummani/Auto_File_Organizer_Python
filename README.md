# File Organizer

## Description

File Organizer is a Python script designed to automatically organize files in a specified directory into subfolders based on their file types. For example, `.csv` files will be moved to a `csv` folder, `.jpg` files to a `image` folder, and so on. This script uses the `os` and `shutil` libraries to achieve file management.

## Features

- Automatically detects and sorts files based on their extensions.
- Creates new subfolders for each file type if they do not already exist.
- Moves files to their respective subfolders.

## Requirements

- Python 3.x
- `os` library (standard library)
- `shutil` library (standard library)

## Installation

No installation is required as this script uses Python's standard libraries. Just download the script and run it.

## Usage

1. **Download the Script:** Save the script to your local machine.
2. **Specify the Directory:** Ensure the `path` variable in the script points to the directory you want to organize.
3. **Run the Script:** Execute the script using Python.

### Example

Place the script in the directory you want to organize or modify the `path` variable to the path of the target directory.

```python
import os
import shutil

# Specify the directory you want to organize
path = "/Users/sanajummani/Desktop/Project_sample/"

folder_name = ['csv files','image files','pdf files','video files']
file_name = os.listdir(path)

for folder in folder_name:
    if not os.path.exists(path + folder):
        os.makedirs(path + folder)
        
for file in file_name:
    if '.csv' in file and not os.path.exists(path + 'csv files/' + file):
        shutil.move(path + file , path + 'csv files/' + file )
    elif '.jpg' in file and not os.path.exists(path + 'image files/' + file):
        shutil.move(path + file , path + 'image files/' + file )
    elif '.pdf' in file and not os.path.exists(path + 'pdf files/' + file):
        shutil.move(path + file , path + 'pdf files/' + file )
    elif '.mp4' in file and not os.path.exists(path + 'video files/' + file):
        shutil.move(path + file , path + 'video files/' + file )
else:
    print("No arrangement needed further!")

```

## Customization

- **Target Extensions:** To customize which file types to sort, modify the script to check for specific extensions.
- **Subfolder Naming:** Change the naming convention for subfolders if needed.

## Troubleshooting

- Ensure you have write permissions for the directory you are organizing.
- Verify the path to the `path` is correct.
- Check if any files are in use, as this may prevent them from being moved.

## Contributing

Feel free to fork this repository and submit pull requests for any enhancements or bug fixes.


---

By following this guide, you should be able to easily organize files in any directory based on their file types. Happy organizing!
