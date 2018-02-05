# Trace Ball
Project 001

## Table of Contents
1. Introduction
2. Development
3. Creation and Implementation
4. Research

## Introduction
This design document showcases the design, development and implementation of "Trace Ball", along with the features and mechanics within the game.

#### Brief Description
It's 1 on 1 in this simple yet intense battle! The aim of the game is to lead your opponent on a wild goose chase. You will be able to change difficulty for more intense action.

#### High-Level Description
A non-playing character NPC (that is a character controlled by the computer) targets the user's mouse position as the player moves across the screen, the game is over once the NPC touches the player's mouse position 3 times.

Code Required: JavaScript

#### The Enemy
* Our enemy is relentless and will chase you down no matter what. There's no reasoning with it!
* As the time increases, so does the speed of the opponent.
* The game is a win if time runs out and you're still alive.
* Don't let him catch you, three strikes and you're out!

## Development

#### User Stories
1. As a user, I would like for the game to be viewable in a browser
2. As a user, I would like to see the UI
3. As a user, I would like there to be my player and enemy on the screen
4. As a user, I would like to control the player in a 2 dimensional environment
5. As a user, I would like to define the level's boundaries
6. As a user, I want the enemy to be able to follow me
7. As a user, I want to be informed of the amount of lives that I have
8. As a user, I want to be informed if I have won/lost

#### Development Timetable
| User Story | Task Description                            | Points | Due Date |
| ---------- |-------------------------------------------- | -------| -------- |
| 1          | View the game in a browser                  | 1      | 22/09    |
| 2          | Design and create the UI                    | 1      | 22/09    |
| 3          | Draw the player and the enemy               | 2      | 22/09    |
| 4          | Receive mouse coordinates to control player | 3      | 22/09    |
| 5          | Create level boundaries                     | 2      | 22/09    |
| 6          | Have enemy follow the mouse                 | 3      | 22/09    |
| 7          | Create life counter                         | 2      | 22/09    |
| 8          | Create Win/Game over screen                 | 2      | 22/09    |

#### Use of Teamwork
The task was to plan out the project in groups then individually create the project individually according to the notes and plans we had written as a team.

I contributed mainly towards the planning, offering user stories to help with upcoming development of the project, so it would be clear what should be created per story.

#### Flowchart
![Flowchart](https://github.com/LBruni98/Project-001/blob/master/Flow%20Chart.png)

Here is the main layout for what I'm trying to do. The flowchart shows the overall creation of the game; the creation of the UI and game characters, canvas, life system and game over. The game draws in the graphics and then the user can start the new game. The flowchart details that if you get hit, you lose a life and if you lose all three, the game is over and the player can start again if they so choose.

## Creation and Implementation

#### Process of Implementation
The way to successfully implement this algorithm is to go at the tasks individually and that way, the whole process is ordered and each task can be fully realized.

The first step to creating the program is to plan out what the initial steps for development; outlining the user stories and creating flowcharts and pseudo-code of the program, generally to understand how it will work and its layout.

Next is to find the IDE and programming language applicable for the program; what will help with the development and what would best suit the program.

Then would be to take the stories and create the program in accordance to the user stories laid out in planning. The program takes shape here and not developing is easier, rather than approaching the program in a huge epic. Along with easier development through individual tasks, the user can also test every individual part for easier testing and can easily understand the structure of the code.

Finally comes to the execution. For this project, it being mostly web based and built around HTML and CSS as well as JavaScript, the code was tested and executed within a web browser along with additional testing to see if the program functioned properly, such as seeing if anything happens if the browser window is resized or scrolled through.

The implementation maybe very rough as I have little to no experiance in coding. Though I did implement each feature and element into the product, most of it was from web research, copying each line of code and trying my best to make the code fit and function well with my product, as well as make it readable. The sites down below were helped me with the construction and implentation of my code. In the future, this will be used mainly as reference for future projects and will help me see where to improve in my coding.

#### IDE
![Notepad](https://github.com/LBruni98/Trace-Ball/blob/master/Notepad.PNG)

The IDE used for this was notepad as a challenge. Notepad is basic, very standard and wouldn't really be considered a proper IDE as there is no error correcting and no syntax. Notepad can be used to create html or JavaScript pages by changing the type of file rather than leaving it at a text file and because of the file types supported, the code can be altered in other IDEs such as Dreamweaver.

#### Coding Standards
Coding Standards are a set of guidelines for a developer to follow in order to create high quality code. These guidelines help a developer write in a specific way that best suits that language. It works because developers would have written in their own style when others would write their code in a different style; different indentation, naming of functions and commenting. If in a workplace environment, setting a standard for coders would help, so to improve readability of the code and helps with editing and modifying.

##### Evaluation
The coding standards in my project almost match what was stated above. I used this in order to make the code readable, not just to me, but also to other who want to read the lines of code, structuring the code in a way to show what does what and what is what. For instance, the start of functions would usually have the "{" symbol by the function to help the user and I to determine the beginning of the function rather than placing said symbol either underneath or positioning the part of the code all on one line. Whenever, I head back into this for reference, the standards that I have adopted will help with distinguishing the code to all people; members of the team, other programmers or myself.

#### Debugging
The only way to verify either or not there is an error is if the JavaScript code refuses to run. There is no way of notepad knowing where the error could be located in the code. However, using the console to find where the errors are located are far more useful. The process of debugging where needed, was to run the program when a specific function would be entered, using the console to find out where the located error is and either alter or comment out the code where the problems were occurring.

#### Development of Code
##### Retrieving Mouse Co-ordinates
Retrieving the co-ordinates of the mouse is important to help with having both the image move alongside the mouse and the enemy to chase the mouse on the page. In javascript, the way I done this was to implement listeners and call those listeners as if it was a function and assign them to pick up the mouse co-ordinates.

```javascript
canvas.addEventListener("mousemove", setMousePosition, false);
 
			function setMousePosition(e) {
				mouseX = e.clientX - canvasPos.x;
				mouseY = e.clientY - canvasPos.y;
			}

```
This set piece of code calls upon a listener and sets the mouse position relative to the players screen and the actual canvas. This is called whenever the mouse moves.

```javascript
//Player's square
				ctx.clearRect(0, 0, canvas.width, canvas.height);
				ctx.beginPath();
				ctx.fillStyle = "#00FF00";
				ctx.fillRect(mouseX, mouseY, 25, 25);                              
				ctx.fill();
```
With the coordinates retrieved, now the shape can now follow the mouse exactly. Here the mouse X and Y values are in placed in the shape's two position coordinates in this line of code `ctx.fillRect(mouseX, mouseY, 25, 25);`

```javascript
				//Enemy's sqaure
				var tx = targetX - x, ty = targetY - y;
				var dist = Math.sqrt(tx*tx+ty*ty);
				var rad = Math.atan2(ty,tx), angle = rad/Math.PI * 180;
				var velX = (tx/dist)*speed, velY = (ty/dist)*speed;
					x += velX
					y += velY
				ctx.beginPath();
				ctx.fillStyle = "#FF0000";
				ctx.fillRect(x, y, 25, 25);
				ctx.fill();
```

The co-ordinates are then used to target my mouse so that the enemy will be able to chase the mouse. The code here notes down the target coordinates, which would be both the shape's and the speed of the enemy is calculated to keep up with the mouse. 

![Mouse Following](https://github.com/LBruni98/Trace-Ball/blob/master/Project%201%20-%20Proof%201.PNG)

The game in action, displaying the shapes in combat. The green square being the player and the red square being the opponent.

## Research

#### References for creation
* Kirupa (2015). Follow the Mouse Cursor. [online]. Kirupa. Available from: <https://www.kirupa.com/canvas/follow_mouse_cursor.htm>. [Accessed 24 September 2017].
* java2s.com [online]. (n.d.). Available from: <http://www.java2s.com/Tutorials/Javascript/Canvas_How_to/Animation/Chase_the_mouse.htm>. [Accessed September 2017].
* w3schools.com [online]. (n.d.). Available from: <https://www.w3schools.com/graphics/game_intro.asp>. [Accessed September 2017].
