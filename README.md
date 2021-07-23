# Bash
1. Bash
* Pipe and redirections
* Bash builtins and other commands 
* Brackets and braces in Bash
* Bash expansions and substittutions
* Brace expansion
* Parameter expansion
* Command substitution
* Arithmetic expansion

2. Programming with bash
* Choosing a text editor for Bash scripting
* Displaying text with echo
* Working with variables
* Working with numbers
* Comparing values with test
* Comparing values with extended test
* Formatting and styling text output
* Formatting output with printf
* Working with arrays

## Exemple: sysreport
* Here at the top I define two variables using command substitution to get the free space on the disk and the free memory. In these I'm using the df and free commands and then I'm piping the output of each into awk. My awk program extracts the second line and from the second line, extracts field number four. Those are the values that I'm interested in. Below that, I define a few variables with formatting codes. 
* Then I use printf to print out a time code and assign that to the variable logdate. Below that I use echo with the dash e option to print a formatted string. This is the header for my report. That's followed by a series of printf commands listing some information that I'm interested in. Using a mix of command substitution, environment variables, and local variables that I set in the script. And here in the last line I use that logdate variable, which was defined by printf a little bit further up. 

3. Bash Control Structures 
* Conditional statements with the if keyword
* Working with while and until loops
* For loops
* Selecting behavior using case
* Using functions
* Reading and writing text files
## Exemple: fortune
* I chose to build a fortune telling game and I decided to include two random elements. When I run the script, I get a response while the program thinks, and then I get my reply. I'll run that a few times. 
* Let's take a look at the script. Here at the top of the program, I have a title. I'm using echo with -e so I can use tab characters to keep everything aligned. I'm also using a little bit of formatting and some emojis. Then I define two variables based on a random value. The first one is a random value between zero and three, and the second is a value between one and 10. 
* Below that, I declare an array called fortunes, which includes 10 fortune strings. Then I use a case statement based on the weighting number variable, which, again, is a random number between zero and three. And for whatever the value of that variable is, I sleep for one second and then print out a statement that makes it seem like the program's thinking harder than it is. 
* And after that, I sleep for a couple more seconds. Who knows how long gazing into the future can take? Below that, I use a blank echo line to add a little bit of space, and then I use parameter substitution on the fortune's array, passing in my random mystery number from one to 10 as the index that I want to read. This is where the random fortune comes from. And after that, I use a blank echo statement to give myself one line before the prompt comes back. 
5. Interacting with the User
* Working with arguments 

* Working with options 

* Getting input during execution 

* Ensuring a response 

## Exemple: multigame

* This game includes three basic games, which can run from a menu, or you can choose to run a particular game by specifying it as an argument at the command line. 
* Let's explore the script. Here ,at the top of the game, I define my games as functions. Here, in a guessing game, I generated a local variable, called mynumber, which is an integer. It's a random number between one and 10. Then I ask the user to guess a number between one and 10. I check their guess against my number. If they get it right, I tell them so. And if not, I say, "Nope, I was thinking of" whatever number I was thinking of. When that's done, I sleep for a second, and then I call the choosegame function, which draws the menu. 
* The coin flip game is similar. I set a local integer variable to either one or two. Then I check to see if that number is equal to one. If it is, then I set the variable face to heads. If not, it's tails. Then I print out the result, pause for a moment, and call the game selector again. In the dice function, which simulates rolling two dice, I generate two local variables, each between one and six. Then I print out the results. Again, I pause for a moment and then call the game chooser. 
* The choosegame function is the primary interface. I'm using a select statement to ask the user to choose either a guessing game, to flip a coin, or to roll some dice. I also give them the option to exit. Then in a case block, I handle each of those responses. For the games, I call the function for whichever game the user selected. If the user gives me a response that I don't recognize, I remind them to please choose from the menu. 
* Because each of my games call this function when they finish, the user comes back here when a game is done. Below that, we'll handle the case that there's an argument provided and jump straight to that game. Here, I'm using the $1 variable to get the first argument after the script name. It can be guess, flip, or dice, and those correspond to the names of the functions that run the games. 
