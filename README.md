# Assembly-Language-Clock
24 Hour clock built for 8086

## Introduction:

This project is a working 24-hour clock written in an assembly language. The program will display a header of “HR MIN SEC” and then the user will be able to input what time they wish to start the clock at. The time that the user inputs will be saved into memory and then the clock will start operating from that point on. The user will only be able to input a 2 digit hour, and a 2 digit minute. The seconds will always start at 00. This clock will operate indefinitely until the user quits the program. This clock runs from 00 00 00 to 23 59 59 and then loops back through again. This clock does not run at exact time but it is very close. 

## Program Logic 

This program has many different procedures that are vital for this program to work. This first procedure at location 0150 is used to clear the screen. The second procedure located at 0180 is used to place the cursor at the top left corner of the console. The third procedure at 0200 is just used to hold the variable “HR MIN SEC”. The next procedure at 0250 is used to get user input from the keyboard, display that input, and then store that input starting at location 1000. The next procedure is a main aspect of the program, located at location 0400 it is used to delay the program about 1 second. This procedure is called over and over again to simulate the clock. The next 6 procedures are used just to place the cursor in specific locations on the second line. 0450 is used to place the cursor at the LSB of the seconds, 0500 is used to place the cursor at the MSB of the seconds, 0550 is used to place the cursor at the LSB of the minutes, 0600 is used to place the cursor at the MSB of the minutes, 0650 is used to place the cursor at the LSB of the hours, and the 0700 is used to place the cursor at the MSB of the hours. The next and last procedure is the main procedure of the program. It is used to make calls to the other procedures. In this procedure located at location 0300 it clears the screen, places the cursor at the top left corner, and then it displays the heading “HR MIN SEC”. After this is done the cursor is then places the cursor to the second line and waits for user input. The user then inputs 2 digit for the hours a space, and then 2 digits for the minutes. After this is done the program then starts to run. It will display the input by the user and add 00 at the end of it. The program is constantly checking to see what values are. Once the LSB of the seconds reaches a 9, the next cycle it will change that value to a 0, and increment the MSB of the seconds. If the MSB of the seconds was a 5, then it gets replaced with a 0 and increments the LSB of the minutes. If the LSB of the minutes was a 9, then it replaces it with a 0 and increments the MSB of the minutes. If the MSB of the minutes was a 5, then it replaces it with a 0 and increments the LSB of the hours. If the hours was a 3, then it checks to see what value of the MSB of the hours was. If it was not a 2, then the program increments the MSB of the hours. If the MSB of the hours was a 2, then it replaces the LSB and MSB of the hours to 0 making the time “00 00 00” clycling through the clock again. If the LSB of the hours was a 9 and the MSB of the hours was not a 2 then it just increments the MSB of the hours, and makes the LSB of the hours a 0.

## How to run

In order to start this program you must start up the debug console on windows. Once in the debug you must paste all of the run code located in clock.txt. After the code is pasted it should automatically run. If not just press enter if the last line says g=300. G=300 will start the program since the main procedure of the program is located at location 300. Once the screen is loaded and displays “HR MIN SEC” you then can enter the hours and minutes to start the clock. YOU MUST ENTER 2 DIGITS FOR THE HOURS AND SECONDS. YOU MUST INCLUDE A SPACE BETWEEN THE HOURS AND SECONDS. In order for this program to run correctly you must enter a valid 24 hour time:
Ex)
00 00 – 23 59

The numbers must be in this range including a 0 if it is just a single digit.

Once you enter the time the clock will start working.

Again, you must enter 2 digit for the hour, a space, and then 2 digits for the minutes. You do not need to press enter, after you input the hours, a space, and the minutes the clock will start working.
