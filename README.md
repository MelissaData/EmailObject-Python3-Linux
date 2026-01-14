# Melissa - Email Object Linux Python3

## Purpose
This code showcases the Melissa Email Object using Python3

Please feel free to copy or embed this code to your own project. Happy coding!

For the latest Melissa Email Object release notes, please visit: https://releasenotes.melissa.com/on-premise-api/email-object/

For further details, please visit: https://docs.melissa.com/on-premise-api/email-object/email-object-quickstart.html

The console will ask the user for:

- Email

And return 

- Mailbox Name
- Domain Name
- Top-Level Domain Name
- Top-Level Domain Description
- Result Codes

## Tested Environments
- Linux 64-bit Python 3.8.7, Ubuntu 20.04.05 LTS
- Melissa data files for 2026-01

## Required File(s) and Programs

#### libmdEmail.so

This is the c++ code of the Melissa Object.

#### Data File(s)
- mdEmail.cfg
- mdEmail.db3

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

This project is compatible with Python3

#### Install Python3
Before starting, make sure that Python3 has been correctly installed on your machine and your environment paths are configured. 

You can download Python here: 
https://www.python.org/downloads/

You can check that your environment is set up correctly by opening a command prompt window and typing the following:
`python3 --version`

![alt text](/screenshots/python_version.PNG)

If you see the version number then you have installed Python3 and set up your environment paths correctly!

----------------------------------------

#### Download this project
```
git clone https://github.com/MelissaData/EmailObject-Python3-Linux
cd EmailObject-Python3-Linux
```

#### Set up Melissa Updater 
Melissa Updater is a CLI application allowing the user to update their Melissa applications/data. 

- In the root directory of the project, create a folder called `MelissaUpdater` by using the command: 

  `mkdir MelissaUpdater`

- Enter the newly created folder using the command:

  `cd MelissaUpdater`

- Proceed to install the Melissa Updater using the curl command: 

  `curl -L -O https://releases.melissadata.net/Download/Library/LINUX/NET/ANY/latest/MelissaUpdater`

- After the Melissa Updater is installed, you will need to change the Melissa Updater to an executable using the command:

  `chmod +x MelissaUpdater`

- Now that the Melissa Updater is set up, you can now proceed to move back into the project folder by using the command:
  
   `cd ..`

----------------------------------------

#### Different ways to get data file(s)
1.  Using Melissa Updater
    - It will handle all of the data download/path and .so file(s) for you. 
2.  If you already have the latest DQS release zip, you can find the data file(s) in there
    - To pass in your own data file path directory, you may either use the '--dataPath' parameter or enter the data file path directly in interactive mode.
    - Comment out this line "DownloadDataFiles $license" in the bash script.
    - This will prevent you from having to redownload all the files.
	
----------------------------------------
### Change Bash Script Permissions
To be able to run the bash script, you must first make it an executable using the command:

`chmod +x MelissaEmailObjectLinuxPython3.sh`

Then you need to add permissions to the build directory with the command:

`chmod +rwx MelissaEmailObjectLinuxPython3`

As an indicator, the filename will change colors once it becomes an executable.

You may also need to alter permissions for the python files. To do this navigate into the MelissaEmailObjectLinuxPython3 directory and run these commands: \
 `chmod +rx MelissaEmailObjectLinuxPython3/MelissaEmailObjectLinuxPython3.py` \
 `chmod +rx MelissaEmailObjectLinuxPython3/mdEmail_pythoncode.py`

## Run Bash Script
Parameters:
- --email: a test email address
 	
  This is convenient when you want to get results for a specific email address in one run instead of testing multiple email addresses in interactive mode.  

- --dataPath (optional): a data file path directory to test the Email Object
- --license (optional): a license string to test the Email Object
- --quiet (optional): add to the command if you do not want to get any console output from the Melissa Updater

- Interactive 

  The script will prompt the user for an email address, then use the provided email to test Email Object. For example:
  ```
  ./MelissaEmailObjectLinuxPython3.sh
  ```
  For quiet mode:
  ```
  ./MelissaEmailObjectLinuxPython3.sh -quiet
  ```
- Command Line 

  You can pass an email in ```--email``` parameter and a license string in ```--license``` parameter to test Email Object. For example:
  ```
  ./MelissaEmailObjectLinuxPython3.sh --email "info@melissa.com" 
  ./MelissaEmailObjectLinuxPython3.sh --email "info@melissa.com" --license "<your_license_string>"
  ```
  For quiet mode:
  ```
  ./MelissaEmailObjectLinuxPython3.sh --email "info@melissa.com" --quiet
  ./MelissaEmailObjectLinuxPython3.sh --email "info@melissa.com" --license "<your_license_string>" --quiet
  ```
This is the expected output from a successful setup for interactive mode:

![alt text](/screenshots/output.png)

    
## Troubleshooting
Troubleshooting for errors found while running your program.

### Errors:
| Error      | Description |
| ----------- | ----------- |
| ErrorRequiredFileNotFound      | Program is missing a required file. Please check your Data folder and refer to the list of required files above. If you are unable to obtain all required files through the Melissa Updater, please contact technical support below. |
| ErrorLicenseExpired   | Expired license string. Please contact technical support below. |


## Contact Us
For free technical support, please call us at 800-MELISSA ext. 4
(800-635-4772 ext. 4) or email us at tech@melissa.com.

To purchase this product, contact Melissa sales department at
800-MELISSA ext. 3 (800-635-4772 ext. 3).
