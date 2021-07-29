# MazeSolver
The idea here is to write a java program to solve the maze. The maze is given in a file under the resource folder and the program reads the file, solves the maze, and prints the path from source to destination if it presents, else it prints "No path available from source to destination" in the console.

# Prerequisites:

Install the latest version of [Java](preferably Java 1.8).
You may need to set JAVA_HOME.
Install Maven and set MAVEN_HOME.

# Compile and Build: 
-> In order to compile and build the project:

1. Navigate to the folder where the project is copied. 
2. Execute the command
   mvn clean
   mvn install
   mvn exec:java

As a result you will get a maze in the console containing the available path from source to destination.
1.  To run the JUnit test cases , please executes the below command:
   mvn test
   
# Implementation Details:
1. First we need to get the coordinates of the source and destination position.
2. Then we start moving from the source (@) to the destination ($).
3. Every time we make choice to move to a particular direction from a point, for ex: Left, right, up, or down.
3. We keep storing the coordinates in a stack. We have used LinkedList implementation to represent the stack.
5. If we reach a point when there is no path available from the choice we made, we backtrack from there and keep popping the coordinates from the stack.
6. By doing so, if we get the path, it prints in the console; otherwise it prints "no path available" in the output console.
7. If the source and destination positions are next to each other then the program can not print the path but it will log the message at INFO level, "The destination is just next to source."

# Its strengths and limitations:
Strength : 
We have used backtrack implementation instead of recursion which results in faster results.
The solution covers few invalid use cases as well. For example: If the input file is not present and if the file has no content.
Limitation:
In one run, the program can handle only one file. It can not solve multiple mazes.
For now, the file path has been hardcoded in the Main class and it does not take filePath from the user. 

# Does your implementation scale:
Since the program does not handle filePath provided by the user, hence we can scale or extend the program to handle the user inputs as well without harming the existing functionality. 

# Is it robust against invalid input?
Yes, we have tried few invalid use cases and covered them in the JUnit test case. 
For example: 
If the input file is not present 
if the file has no content.
