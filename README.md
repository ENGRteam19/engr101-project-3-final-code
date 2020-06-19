1.) Download and install the MinGW compiler (instructions below) and MinGW SFML for windows https://www.sfml-dev.org/download/sfml/2.5.1/
2.) Unzip the SFML file into a new folder
3.) Rename to ‘SFML’
4.) Download and unzip AVC_Win10.zip into this same folder
5.) Download Geany (instructions below)
6.) Open ‘makefile’ and ‘robot.cpp’ through Geany in the AVC_robot folder
7.) Change the makefile txt to the following:
INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib
robot.exe: robot.o 
	g++ $(LIBS) -o robot robot.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network 
robot.o: robot.cpp
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

INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib
robot.exe: robot.o 
	g++ $(LIBS) -o robot robot.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network 
robot.o: robot.cpp
	g++  -c $(INCLUDE) robot.cpp 
  
To:

INCLUDE = -I C:\Users\HP\Documents\University\ENGR101\robot2\SFML\include
LIBS = -L C:\Users\HP\Documents\University\ENGR101\robot2\SFML\lib
robot.exe: robot.o 
	g++ $(LIBS) -o server3 server3.o -lsfml-window  -lsfml-graphics -lsfml-system -lsfml-network 
server3.o: server3.cpp
	g++  -c $(INCLUDE) server3.cpp 
19.) Delete server3.o and server3.exe in the AVC_server folder
20.) Open server3.cpp and press ‘make all’ like before
21.) This should compile successfully
22.) To run the actual robot, I suggest you close all geany files and open server3.cpp again and the robot.cpp in a new instance of geany
23.) Press build then make and execute server3.cpp and then open robot.cpp and execute this too. Click on the Global view window and your robot should be running
24.) To change the courses between core, completion, and challenge, open cofig.txt in the AVC_server folder and change ‘core.txt’ to any of these on line 1 then save this txt file
“mazeFile,core.txt / “mazeFile,completion.txt / mazeFile,challenge.txt

25.) Each time you want to run the robot from now on, begin from step 19
