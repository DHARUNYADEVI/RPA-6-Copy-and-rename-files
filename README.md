# RPA-6-Copy-and-rename-files
## NAME: Dharunyadevi S
## REGISTER NUMBER: 212223220018
# AIM:
To create a UiPath workflow that copies all files from a source folder to a destination folder and renames them by appending a timestamp to each file name.

# ALGORITHM:
Step 1: Create a New Process Open UiPath Studio and create a new process named CopyRenameFiles.

Step 2: Create Input Variables Create the following variables in the Variables panel:

Name : Type Default Value (optional) sourceFolder : String "C:\Users\YourName\Documents\SourceFiles" destFolder : String "C:\Users\YourName\Documents\RenamedFiles" files : String[] (leave blank)
Step 3 : Get All Files from Source Folder Drag an Assign activity: files = Directory.GetFiles(sourceFolder)

Step 4: Use For Each to Loop Through Files i. Add a For Each activity. ii. ForEach item: file In files iii. Set TypeArgument to String.

Step 5: Inside the Loop – Generate Timestamp Add an Assign activity inside the loop:

timeStamp = Now.ToString("yyyyMMdd_HHmmss")
Create a timeStamp variable of type String.
Step 6: Get File Name and Extension

Add two Assign activities: fileName = Path.GetFileNameWithoutExtension(file) extension = Path.GetExtension(file) (Create fileName and extension variables of type String)
Step 7: Build New File Name Add Assign:

newFileName = fileName + "_" + timeStamp + extension (Create newFileName as a String variable)
Step 8: Copy File to Destination Folder

Add another Assign: destPath = Path.Combine(destFolder, newFileName) (Create destPath as a String variable)
Then use Copy File activity: From: file To: destPath

# PROGRAM:

<img width="1396" height="718" alt="image" src="https://github.com/user-attachments/assets/140869a8-5a6a-4892-ad67-87806e038df8" />

<img width="1400" height="936" alt="image" src="https://github.com/user-attachments/assets/17c61aa1-8211-448e-904f-cbad048c1692" />


# OUTPUT:
### source_folder

<img width="1917" height="704" alt="image" src="https://github.com/user-attachments/assets/4a50382a-e52a-4b88-a1cb-d98097eb2393" />

### destination_folder

<img width="1907" height="703" alt="image" src="https://github.com/user-attachments/assets/066313ac-c777-4aa1-ac42-4d8ed6b7874a" />

# RESULT:
The UiPath workflow successfully reads all files from a source folder, appends a timestamp to each file name, and copies them to a new destination folder.
