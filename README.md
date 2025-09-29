# Playing blu ray discs using VLC windows guide
This process has been tested on Windows 10 ver. 22H2 (OS build 19045.6332)
using the 64 bit version of VLC | AMD CPU

### Preface
This may not be the best nor the official way to do this. This initially started as a txt file to remind myself how to do it. I figured i should share what I found since it turns out a lot of other people seem to face the same problem.  

The idea behind this repo is to have the required files and a beginner-friendly guide all in one convinient place to be as comprehensive as possible and easy to follow.
This was made because most Software that iI've seen that claims it can run bluray's either lie, charge more than they are worth or sometimes both. 
Most of the resources/guides for VLC I found are either out-of-date, don't work anymore, or just miss crutial details or have poor documentation (its possible that i am just dumb :p) with the occasional important resources intermitently not being accessable anymore.
(this may not be the case anymore it has been a while since i initially made this guide)


NOTE: this does not work 4k blu ray discs. thats a whole other beast that is even more confusing and complex than just getting a blu ray disc to run

## Windows 

### Steps
*this guide assumes you are using a 64 bit version of windows,already have a blu ray player and have installed the 64 bit version of VLC*

For VLC to play bluray's you need following files:
- `keysdb.cfg` file, `libaacs.dll` file and `libbdplus.dll` which need to be place in their respective correct directories 
- the correct version of java runtime enviroment that blu rays use. 

These files should be included within this guide. 


================ 
INSTALLING Java8
----------------

blu rays run on java because write once run 
everywhere mentality java has. however it is version specific,
running on java ver. 8 
inside the folder there is the correct
java version, just the enviroment (JRE) not the JDK
included for convinience. its from the official java website but
you can download a copy from java directly
- run the java installer. 

================ 
INSTALL libaacs.dll & libbdplus.dll file
----------------
- find the vlc directory, path usually being
`C:\Program Files\VideoLAN\VLC`
- copy the libaacs.dll, libbdplus.dll and paste it into the vlc directory

**NOTE:**
 libaacs.dll (vital) and libbdplus.dll (optional) are libraries used for Blu-ray disc decryption

================ 
INSTALL keysdb.cfg file
----------------
*I noticed that there is two ways of doing this. they both seem to work exactly the same. if i had to guess using ProgramData path makes it global for all users, while AppData is local for that user. Probably better to do ProgramData* 

###ProgramData route###
- go to the ProgramData directory, the path being
`C:\ProgramData`
- create a folder called "aacs"
- inside the aacs folder (`C:\ProgramData\aacs`) paste the keysdb.cfg
  
##AppData route###
- go to the AppData Roaming directory, the path being
`C:\Users\<Your UserName>\AppData\Roaming`
- create a folder called "aacs"
- inside the aacs folder (`C:\Users\<Your User Name>\AppData\Roaming\aacs`) paste the keysdb.cfg

there should be a copy of the latest keys file in this folder, the lastest publicly available one is 50.9Mb big (as of writing this) 


**NOTE:**

the AppData and ProgramData directory in windows are set as a hidden folder, meaning you cannot by default navigate to it. 
To find/access it you can do either of the following:
  1. Change file explorer to show hidden items by opening file explorer, clicking on the view tab at the top of the window
  check the "Hidden items" box in the show/hide section. Then navigate through the directory   

  2. Use the shortcut Win + r OR windows search and type 
  `%appdata%` or `%programdata%`

  3. Copy the path and replace `<Your UserName>` with your actual username on your computer. paste in file explorer path


================ 



#### Credit
I did not create or write any of the files inside this repo. Only the README.md, credit goes to those who made it:
* https://vlc-bluray.whoknowsmy.name/ | README.md file took heavy inspiration from this guide. sadly the included files are out of date and i think the website has been abandoned. 
* java runtime enviroment ver. 8 | Oracle 
* libaacs.dll & libbdplus.dll | stolen from makeMKV, both initially called libmmbd64.dll (just renamed it)
* keydb.cfg | idk, i think i found it on a forum but that was a while ago
