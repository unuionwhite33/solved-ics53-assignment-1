Download Link: https://assignmentchef.com/product/solved-ics53-assignment-1
<br>
You will write a text adventure game. The idea of a text adventure game is that the player is in a virtual room in a “dungeon”, and each room has a text description associated with it, such as, “This room in big and brightly lit. It has doors on the north and west walls”. The player can move from room to room using compass directional commands.




Your program will be a function called adventure which takes no arguments and returns no values. Your function adventure will allow the user to enter commands related to moving through the dungeon and interacting with objects. Your function should print out a prompt to indicate that the user can enter a command. Your prompt should be a ‘$’ character. At the prompt the user will type a command followed by a set of arguments for the command. Your function will perform whatever action is indicated by the command, and then your program will print a ‘$’ character on a new line in order to let the user know that he/she can type a new command. If the command is a compass command which moves the player into a new room, your program will print the description of the room before printing the ’$’ character on the next line.

<h2>Dungeon File</h2>

The rooms in the dungeon, and their arrangement, is stored in a <em>dungeon file</em>. When the game starts, the player will have to issue a command to load a dungeon file describing the dungeon. The dungeon file will be a text file containing information about each room in a specific format. Each non-empty line of the file will contain information about a single room in the dungeon. Each room is associated with the following 6 fields of information.

<ol>

 <li><strong><em>Room number</em></strong>: This is a positive integer which uniquely identifies the room.</li>

 <li><strong><em>Description</em></strong>: This is a string which is printed when the player enters the room. Each string is delimited with the ‘+’ character rather than a traditional quote. This means that a ‘+’ character cannot be included inside the string.</li>

 <li><strong><em>North room</em></strong>: This is the room number of the room immediately to the north of this room. If there is no room to the north of this room then this value is -1.</li>

 <li><strong><em>South room</em></strong>: This is the room number of the room immediately to the south of this room. If there is no room to the south of this room then this value is -1.</li>

 <li><strong><em>East room</em></strong>: This is the room number of the room immediately to the east of this room. If there is no room to the east of this room then this value is -1.</li>

 <li><strong><em>West room</em></strong>: This is the room number of the room immediately to the west of this room. If there is no room to the west of this room then this value is -1.</li>

</ol>




All 6 fields of information about each room are contained in order on a single line in the dungeon file. Each field of information is separated by one or more spaces. The room described on the first line of the file is the initial room where the player will start after the dungeon file is loaded.




Here is an example dungeon file. Be aware that this is only an example and that your code must work with any valid dungeon file.




<ul>

 <li>+This is an open field west of a white house, with a boarded front door.+ 2 -1 -1 -1</li>

 <li>+North of House: You are facing the north side of a white house.+ -1 1 3 -1</li>

 <li>+Behind House: You are behind the white house.+ -1 4 -1 2</li>

 <li>+South of House: You are facing the south side of a white house.+ 3 -1 -1 -1</li>

</ul>




Your program should accept the following command related to dungeon files:

<ol>

 <li><strong>loaddungeon</strong>: This command reads a dungeon file, allowing the player to explore the dungeon.</li>

</ol>

The function takes one argument, the name of the dungeon file. The function returns no values. After executing this command, the rooms of the dungeon should contain no items. The loaddungeon command can only be issued once. If the player tries to issue the command a second time, the error “Dungeon already loaded” should be printed.




<h2>Moving Through the Dungeon</h2>




The program must keep track of the <em>current room</em> which is the room which the player is currently in. After executing the loaddungeon command, the <em>current room</em> should be the room described on the first non-empty line of the dungeon file. The player will enter compass direction commands to move from one room to another. Your program should accept the following commands related to movement:




<ol>

 <li><strong>north</strong>: This command moves the player into the room to the north of the current room. If there is a room to the north then the description of the new room is printed. If there is no room to the north then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>south</strong>: This command moves the player into the room to the south of the current room. If there is a room to the south then the description of the new room is printed. If there is no room to the south then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>east</strong>: This command moves the player into the room to the east of the current room. If there is a room to the east then the description of the new room is printed. If there is no room to the east then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>west</strong>: This command moves the player into the room to the west of the current room. If there is a room to the west then the description of the new room is printed. If there is no room to the west then the message, “You can’t go there.” is printed to the screen.</li>

</ol>

<strong> </strong>

<strong> </strong>

<h2>Command Summary</h2>

<strong> </strong>

This is a summary of all of the commands that your program should accept.

<ol>

 <li><strong>loaddungeon</strong>: This command reads a dungeon file, allowing the player to explore the dungeon.</li>

</ol>

The function takes one argument, the name of the dungeon file. The function returns no values. The loaddungeon command can only be issued once. If the player tries to issue the command a second time, the error “Dungeon already loaded” should be printed. After executing the loaddungeon command, the <em>current room</em> should be the room described on the first non-empty line of the dungeon file.

<ol start="2">

 <li><strong>north</strong>: This command moves the player into the room to the north of the current room. If there is a room to the north then the description of the new room is printed. If there is no room to the north then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>south</strong>: This command moves the player into the room to the south of the current room. If there is a room to the south then the description of the new room is printed. If there is no room to the south then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>east</strong>: This command moves the player into the room to the east of the current room. If there is a</li>

</ol>

room to the east then the description of the new room is printed. If there is no room to the east then the message, “You can’t go there.” is printed to the screen.

<ol start="5">

 <li><strong>west</strong>: This command moves the player into the room to the west of the current room. If there is a room to the west then the description of the new room is printed. If there is no room to the west then the message, “You can’t go there.” is printed to the screen.</li>

 <li><strong>quit: </strong>This command should end the program.</li>

</ol>

<strong> </strong>

<h2>Example Output</h2>




The following is a running example showing how your program should respond to commands. The text typed by the user is in bold. In the example below, we assume that the contents of dfile.txt are the example dungeon file shown above in the <strong>Dungeon File</strong> section of the homework.

$ <strong>loaddungeon dfile.txt</strong>

This is an open field west of a white house, with a boarded front door.

$ <strong>north</strong>

North of House: You are facing the north side of a white house. $ <strong>east</strong>

Behind House: You are behind the white house.

$ <strong>south</strong>

South of House: You are facing the south side of a white house.  $ <strong>quit </strong>


