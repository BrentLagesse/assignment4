# assignment4

For this assignment you will implement a simplified stack-based CPU with a program queue. You must implement your own stack and queue data structures (do not use std::stack or std::queue).  Your stack and queue data structures must use smart pointers.   They only need to support the functionality necessary to run the driver program. Your program will read in a program and produce an output. Your CPU must implement the following functionality:

void LoadProgram(string filename) -- loads a program stored in the filename into the instruction queue. Ensures that the stack is empty and any previous program is removed.
int Run() -- runs every instruction from the queue and returns the final value (the only one left in the stack).  If there is more than one value in the stack after the program has completed, throw an error.
int Next() -- runs the next line from the queue of the program and returns 0. If there are no more lines it returns -1.
Overload the << operator -- prints the current stack and any instructions remaining in the instruction queue.

Your CPU must support the following language. All values are only integers.  If an operation takes two inputs from the stack and there aren't two inputs, then throw an error.

PSH val -- pushes val onto the stack.
ADD -- Pops the top two values from the stack and pushes the sum of them onto the stack

MULT -- Pops the top two values from the stack and pushes the product of them onto the stack
SUB -- Pops the top two values from the stack and pushes the difference of the second value minus the first onto the stack

DIV -- Pops the top two values from the stack and pushes the second value divided by the first onto the stack (note: only the integer portion).  Div by 0 should throw an error.
CMP -- Pops the top two values from the stack.  If the first is greater than the second, push 1.  If they are equal, push 0, if the second is greater than the first, push -1.

The Grader has requested that you name your directory in the following form:

Student name followed by assignment and number - like 'Balaprasanth_Ramisetty_Assignment_3') and put it in a zip file with the same name.

$ Turn in --

CPUDriver.cpp -- provided by me  

test.sh -- provided by me (you can modify this if necessary)  

Prog1.asm -- provided by me  

Prog2.asm -- provided by me  

cpu.h, stack.h, queue.h -- your header files 

cpu.cpp, stack.cpp, queue.cpp -- your implementations

 

 

# Grading --

To receive credit, your code must compile, it must not segfault or run indefinitely. Do not leave debug statements in your code or the grader will deduct points.  The grading rubric focuses on the CPU functionality itself, but the quality of your queue and stack implementations will also be assessed.

 

LoadProgram -- 10 points
Gets the file, loads the file into some data structure and makes sure the stack is empty

Run/Next -- 20 points total
Runs the program either 1 instruction at a time (next) or until the code is done (run).  Ensure they wrote the code for the appropriate errors/return values.

<<  -- 20 points
    Make sure it prints all the values in the stack and queue
   
5 points each (30 total) for

PSH -- pushes the value on the stack.

ADD/MULT/SUB/DIV/CMP -- Must Pop the top two values, do the computation, then push the result back on the stack.

Code style and comments --  10 points

Git etiquette -- 10 points
Standard good comments about functionality and the specifications for the functions and proper git commit etiquette
