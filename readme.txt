This was tested using SWI-Prolog from the command prompt under windows.
All the predicates for this project are contained in a single file, escape_maze.pl

To run:
swipl escape_maze.pl

At the prompt, run a test as follows:

gen_map(4,10,10,M), display_map(M),find_exit(M,Actions).

This will display a maze as well as the Actions to escape.
