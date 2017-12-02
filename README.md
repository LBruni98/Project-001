# Trace Ball

## Introduction
This design document showcases the design, development and implementation of "Trace Ball", along with the features and mechanics within the game.

#### Brief Description
It's 1 on 1 in this simple yet intense battle! The aim of the game is to lead your opponent on a wild goose chase. You will be able to change difficulty for more intense action.

#### High-Level Description
A non-playing character NPC (that is a character controlled by the computer) targets the user's mouse position as the player moves across the screen, the game is over once the NPC touches the player's mouse position 3 times.

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
| 8          | Create "You win"/Game over screen           | 2      | 22/09    |

#### Flowchart
![Flowchart](https://github.com/LBruni98/Project-001/blob/master/Flow%20Chart.png)

## Creation and Implementation

#### IDE
![Notepad]()

The IDE used for this was notepad as a challenge. Notepad is basic, very standard and wouldn't really be considered a proper IDE as there is no error correcting and no syntax. Notepad can be used to create html or JavaScript pages by changing the type of file rather than leaving it at a text file and because of the file types supported, the code can be altered in other IDEs such as Dreamweaver.

#### References for creation
* https://www.kirupa.com/canvas/follow_mouse_cursor.htm
* http://www.java2s.com/Tutorials/Javascript/Canvas_How_to/Animation/Chase_the_mouse.htm
* https://www.w3schools.com/graphics/game_intro.asp
