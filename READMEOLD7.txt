Name: Peter Koncelik
Email: peter.e.koncelik@vanderbilt.edu

PA7 README File

This project uses Stack and Queue Data Structures to solve a maze: these mazes are composed of '#' characters symbolizing the walls, a
'*' symbolizing the entry point, and a degree symbol as the exit. Functionality was extended in providing a visualization of the solver's
progress as the program progressed in marking visited grid locations: this is best seen by running the program from the command
line using the g++ compiler.

Testing was an important aspect of the implementation and completion of this project. For testing my Stack and Queue classes,
after creating their templated versions, I implemented them into projects 5 and 6, respectively, ensuring that the basic class
functions remained proper and functional. I then tested my final program first by using a variety of .txt mazes: in addition to
the two supplied mazes, I also tested functionality on mazes supplied from Piazza, while also creating my own mazes to test certain
edge conditions, such as a boundless or an unsolvable maze. Lastly, I implemented the trace code for the visualization of my MazeSolver
function, which helped me more directly see my code at work.

After testing both FIFO and LIFO agenda methods on a variety of mazes, I came to the conclusion that the LIFO, or stack-based, agenda
seemed to be faster at finding the solution for a given maze. Upon further analysis and use of the trace visualization, this appears
to be the case due to the different ways the FIFO and LIFO agendas go about their maze exploration. The LIFO agenda, because it adds
and removes data from the same end of the agenda, explores the maze in a more linear fashion, traveling along a wall or edge until
another is reached, and then exploring along another egde. In contrast, the FIFO agenda explores its maze by a fan-out approach due
to the two ended add and remove operations on the Queue, spreading its exploration more widely and not following the "corridors" or
bounds of a maze. Therefore, particularly in mazes with a greater number of walls and corridors, a LIFO agenda solves the maze in less
location visits, or in a faster time, by traveling along limited spaces in a more linear fashion, whereas the FIFO agenda covers more
ground and checks more points, increasing its location visit count and slowing down its solution speed.

The FIFO and LIFO agendas respond very differently when the program fails to mark maze locations as visited. Although removing the code
section that marks locations as visited exponentially hinders the program execution to the point of disuse, the program theoretically
should still be able to determine the solvability of a maze, depending on the selected agenda. Particularly, if the user selects the LIFO,
or Stack-based, agenda to be used in a program that doesn't mark visited locations, solvability could not be determined. This is due to the
nature of the Stack/LIFO data structure. Specifically, because the addition and removal of points occur at the same end of the structure,
the LIFO agenda will walk its explored points linearly until a wall hits, and continue in another direction until a corner is hit. At that
point, if locations were not marked as visited, the Stack would infinitely remove, add, and explore the same corner point to the agenda,
therefore "stuck" in the corner of a maze and unable to determine its solvability. Contrastingly, if a FIFO, or Queue-based agenda were
used in a program that did not mark visited locations, the solvability of a maze could still be determined. Because the FIFO structure adds
and removes data points from two different ends, the issue of getting "stuck" is not a problem. The FIFO method would fan out and continue
to test all of the points in the maze, until eventually a solution was found. Despite an incredibly high runtime as a result, the FIFO/Queue
agenda could technically determine the solvability of a maze without marking locations as visited, while the LIFO/Stack agenda could not.


