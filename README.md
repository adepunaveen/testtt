Automate - Assessment 

Setup Steps
1.	Git clone git@github.com:adepunaveen/automate-assessment.git
2.	Docker-compose build
3.	Docker-compose up
Prerequisites
1.	Docker installation
API’s
1.	Below API is used for registering a user in app
http://127.0.0.1:3000/api/user/register POST 
{
    "email": "admin@automate.com",
    "password": "password",
    "name": "admin"
}
2.	Below API is used to login into app. On successful login, token is returned in response which should be used in access all the API’s
http://127.0.0.1:3000/api/user/login POST
{
    "email": "admin@automate.com",
    "password": "password",
}
3.	API is used for creating folder. 
http://127.0.0.1:3000/api/folder/createfolder POST
{
    "foldername":"new folder"
}
4.	API for creating file, if a file is root folder then provide filepath as “/”
http://127.0.0.1:3000/api/file/addfile POST
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
http://127.0.0.1:3000/api/file/movefile POST
{
    "filename":"outside-test.txt ",
    "targetfolder":"new folder"
}

6.	API to get the files of folder
http://127.0.0.1:3000/api/folder/getfiles/<folder name> GET
http://127.0.0.1:3000/api/folder/getfiles/new folder GET
7.	API to get the list of folders and files of a user
http://127.0.0.1:3000/api/dashboard GET
