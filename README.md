0x19. C - Stacks, Queues - LIFO, FIFO

Setup
####Monty interpreter This command will be used to compile the monty interpreter: gcc -Wall -Werror -Wextra -pedantic *.c -o monty Please use gcc-4.8

####Brainfuck programs To Install the brainfuck interpreter: sudo apt-get install bf

Usage
####Monty interpreter The Monty language is a very simple programming language. Monty relies on a unique stack of integers and performs some operations.
Usage is : ./monty FILE where FILE contains lines of commands.
Lines are of the type opcode [argument].
Current opcodes are:

push push onto stack. This opcode is the only one requiring an argument. This argument must be an integer.
pall print all stack.
pop pop the value at the top of the stack.
pint peek the top of the stack.
pchar peek, turning the value into an ascii character if possible.
add pop the 2 elements at the top, push the result of the addition on the stack.
sub pop the 2 elements at the top, push the result of the subtraction on the stack.
mul pop the 2 elements at the top, push the result of the multiplication on the stack.
div pop the 2 elements at the top, push the result of the division on the stack.
mod pop the 2 elements at the top, push the modulo on the stack.
swap swap the top 2 elements of the stack.
rotl move the top element to the bottom of the stack.
rotr move the element at the bottom of the stack to the top.
pstr print the whole stack as a string if possible.
queue change the functionment of the stack to one of a queue. Enqueue to the bottom of the stack and dequeue from the top.
stack is the reverse of queue, it reestablishes the stack.
nop does not do anything

The Monty language allows for any space before or after the opcode and its argument. Any text after the argument is disregarded. Any line starting with a `#` is considered a comment. Currently the stack is implemented as a doubly linked list. For calculations. If `a` is the first value popped and `b` the second one, the expression evaluated is `b` operator `a`. Hence `a` must be not `0` for divisions and modulo. If the user attempts to perform an illegal operation an error message is displayed and the program exits with status `EXIT_FAILURE`.
####Brainfuck program in the brainfuck folder: bf FILE.

Description of Files
monty.h
header file for the project, contains the structs used throughout.
main.c
Entry point of the interpreter. Feeds a line at a time to `execute`
execute.c
Dispatch the line received from main to the function behind the opcode.
push_and_pop.c
Contains `push` and `pop` opcodes
calculations.c
contains `add`, `sub`, `mul`, `div` and `mod` opcodes.
print_functions.c
Contains `pint`, `pall`, `pchar` and `pstr` opcodes.
nopandqueue.c
Contains `nop`, `stack` and `queue` opcodes.
move_elements_functions.c
Contains `swap`, `rotr` and `rotr` opcodes.
basic_linked_list_functions.c
The stack is implemented as a doubly linked list. This file contains the functions needed to add elements, remove elements and free a doubly linked list.
helpers.c
This file contains helper functions to deal with a string.
getline.c
Our implementation of getline to read a line from a file.
brainfuck/
The brainfuck folder contains:
1000-holberton.bf
Print `Holberton` in bf.
1000-add.bf
Add 2 single digit numbers whose result is less than 10 in bf.
1000-mul.bf
Multiply 2 single digits numbers whose result is less than 10 in bf.

Author
Ogunmola Samuel Olushola