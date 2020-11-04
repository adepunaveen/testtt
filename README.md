Automate - Assessment 

Setup Steps
1.	Git clone git@github.com:adepunaveen/automate-assessment.git
2.	Docker-compose build
3.	Docker-compose up
Prerequisites
1.	Docker installation
API’s


1.	Below API is used for registering a user in app
URL: http://127.0.0.1:3000/api/user/register 
METHOD: POST
BODY: 
{
    "email": "admin@automate.com",
    "password": "password",
    "name": "admin"
}


2.	Below API is used to login into app. On successful login, token is returned in response which should be used in access all the API’s
URL: http://127.0.0.1:3000/api/user/login 
METHOD: POST
BODY: 
{
    "email": "admin@automate.com",
    "password": "password",
}


3.	API is used for creating folder. 
URL: http://127.0.0.1:3000/api/folder/createfolder 
METHOD: POST
BODY: {
    "foldername":"new folder"
	}
	
	
4.	API for creating file, if a file is root folder then provide filepath as “/”
URL: http://127.0.0.1:3000/api/file/addfile 
METHOD: POST

Example:1
{
    "filename": "test.txt",
    "content": "this is folder file content",
    "filepath":"new folder"
}

Example:2
{
    "filename": "outside-test.txt",
    "content": "this is root file content",
    "filepath":"/"
}


5.	API for moving file 
URL: http://127.0.0.1:3000/api/file/movefile 
METHOD: POST

{
    "filename":"outside-test.txt ",
    "targetfolder":"new folder"
}

6.	API to get the files of folder
URL: http://127.0.0.1:3000/api/folder/getfiles/<folder name> 
METHOD: GET

URL: http://127.0.0.1:3000/api/folder/getfiles/new folder 
METHOD: GET

7.	API to get the list of folders and files of a user
http://127.0.0.1:3000/api/dashboard GET
