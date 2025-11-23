11/17/2025   6:14PM

Initial commit

11/18/2025  7:23PM

Installed SWI-Prolog and checked in the test.pl file provided with the project. 
Tried running the test script and familiarized myself with it.


11/20/2025  4:16PM

display_map predicate of the test file does not display properly. Swapped out the strange
symbols with fixed width standard ASCII characters. Using [] for the wall symbol.

Sample of run with new characters, no longer looks like trash.

swipl test.pl
Welcome to SWI-Prolog (threaded, 64 bits, version 10.0.0)
SWI-Prolog comes with ABSOLUTELY NO WARRANTY. This is free software.
Please run ?- license. for legal details.

For online help and background, visit https://www.swi-prolog.org
For built-in help, use ?- help(Topic). or ?- apropos(Word).

1 ?- show_random_map(4,10,10).
   +--------------------+
   |          []    []  |
   |E         []    []  |
   |                []  |
   |          []    []  |
   |          []    []  |
   |[][][][]  []        |
   |          []    []  |
   |[][][][][][][]  []  |
   |        []  []  []  |
   |    []        S []  |
   +--------------------+


   11/22/2026   8:53PM

   First need to find the start point. Added a find_start predicate using the prolog method find_value to search for the "s".

   gen_map(4,10,10,M),display_map(M),find_start(M,StartCoord).
Correct to: "test:display_map(M)"? yes
Correct to: "test:find_start(M,StartCoord)"? yes
   +--------------------+
   |        []          |
   |[][][]  []    []    |
   |        []  [][][][]|
   |    []  []  []      |
   |    []  []        S |
   |[]  [][][]  []      |
   |    []  E   []  [][]|
   |        []          |
   |    []  []    []    |
   |    []  []          |
   +--------------------+
M = [[f, f, f, f, w, f, f, f|…], [w, w, w, f, w, f, f|…], [f, f, f, f, w, f|…], [f, f, w, f, w|…], [f, f, w, f|…], [w, f, w|…], [f, f|…], [f|…], […|…]|…],
StartCoord = coord(4, 9)


