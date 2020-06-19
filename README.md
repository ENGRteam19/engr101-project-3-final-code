Instructions for making the robot run on Windows:

1.) Download and install the MinGW compiler (instructions below) and MinGW SFML for windows https://www.sfml-dev.org/download/sfml/2.5.1/

2.) Unzip the SFML file into a new folder

3.) Rename to ‘SFML’

4.) Download and unzip AVC_Win10.zip into this same folder

5.) Download Geany (instructions below)

6.) Open ‘makefile’ and ‘robot.cpp’ through Geany in the AVC_robot folder

7.) Change the makefile txt to the following:

INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include<br/>
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib<br/>
robot.exe: robot.o<br/>
        g++ $(LIBS) -o robot robot.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network<br/>
robot.o: robot.cpp<br/>
        g++  -c $(INCLUDE) robot.cpp 

Where the file path on line 1 (INCLUDE) is the path to your SFML include file, and the path on line 2 is your SFML lib file. Change the address on your makefile to associate with the location you have chosen to put your files. Make sure you have a tab indent before both g++ and not spaces.

8.) Delete robot.o and robot.exe in the AVC_robot folder

9.) Open robot.cpp and click the downward arrow on the right of the build button. Then click set build commands

10.) Change the first make command to ‘mingw32-make’ and press OK

11.) Go to the arrow down by the ‘Build” on the tabs at the top of geany.

12.) Click onto “Set Build Commands” on the drop down

13.) Change the “Make” on the top of the second lot of seconds and change the contents to “mingw32-make’

14.) Click the same downward arrow next to the build like before and press ‘make all’

15.) After this is done, robot.cpp should compile successfully

16.) Now open the makefile and server3.cpp in the AVC_server folder through geany like you did with the robot ones

17.) Copy the makefile from the AVC_robot folder and paste it into the makefile for AVC_server

18.) Replace all ‘robot’ with ‘server3’ like below

INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include<br/>
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib<br/>
robot.exe: robot.o<br/> 
	g++ $(LIBS) -o robot robot.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network<br/> 
robot.o: robot.cpp<br/>
	g++  -c $(INCLUDE) robot.cpp<br/> 
  
To:

INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include<br/>
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib<br/>
robot.exe: robot.o<br/> 
	g++ $(LIBS) -o server3 server3.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network<br/> 
server3.o: server3.cpp<br/>
	g++  -c $(INCLUDE) server3.cpp<br/> 
	
19.) Delete server3.o and server3.exe in the AVC_server folder

20.) Open server3.cpp and press ‘make all’ like before

21.) This should compile successfully

22.) To run the actual robot, I suggest you close all geany files and open server3.cpp again and the robot.cpp in a new instance of geany

23.) Press build then make and execute server3.cpp and then open robot.cpp and execute this too. Click on the Global view window and your robot should be running

24.) To change the courses between core, completion, and challenge, open cofig.txt in the AVC_server folder and change ‘core.txt’ to any of these on line 1 then save this txt file
“mazeFile,core.txt / “mazeFile,completion.txt / mazeFile,challenge.txt

25.) Each time you want to run the robot from now on, begin from step 19
.
.
.
Instructions for MinGW compiler:

1.) Download MinGW for windows through: https://sourceforge.net/projects/mingw-w64/files/mingw-w64/

2.) Download and run file https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe
(It should start installing automatically after you've clicked the link)

3.) If you need Administrator rights to do it, right-click file and click "Run as Administrator" from drop down menu
This should install MinGW

4.) Search for it through checking folders like C:\\MinGW or C:\\Users\YourUserName\MinGW or C:\\Program Files\MinGW etc
Click on this folder until you find one called “bin” and find c++.exe

5.) Copy the path by right-clicking the path bar of File Explorer and select Copy as text from pop-down menu

6.) Now open your computer Settings and search environment

7.) Click Set environmental variables from the menu and dialog box should appear

8.) Click PATH, Edit, then New. Go to the next empty line and paste the path you previously copied (ctrl-v)

9.) Double check that folder name is pasted into this line!

10.) Close the dialog box by pressing OK and restart your computer
.
.
.
Instructions for using Geany:

https://osdn.net/projects/mingw/releases/

1.) Install the Mingw software associated with your pc (mingw-get-setup.exe)

2.) Click next on the install page and agree to the license agreement

3.) Close the current version

4.) Reopen and choose the components that you need and run the compiler to check if it is working properly. Otherwise you are able to run the installer again to add more components.

5.) Use the default destination folder (C:\MinGW).

https://www.geany.org/download/releases/

6.) Download Geany for your operating system with the above link. (Windows/Linux/Mac)

7.) Restart computer before using.
