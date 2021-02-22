# Conway-s-Game-of-Life
jp4718
1) Resetting the array. 
   The array used is a1. put a1 before a few functions that configure the starting formation for a1.
   These are reset0 , reset1 , reset01 . reset0 and reset1 fill the array with zeros and ones. reset01 will fill the array randomly with zeros or ones.
   
   SOme more functions that reset the configuration of a1 are stable1 , line4  , blinker , line5  , floater , topline3 and methuselah1 .
   Use these functions of the form:       a1 function .
   eg. a1 reset01
   
   The starting array can be further manipulated using array_!
   of the form : 1 x y a1 array_! 
   where x y is the coordinate you would like to turn into a one. 
   x starts at 1 and moves right, y starts at 1 and moves down. eg. (1,1) is the top left element of the array.
   
2) Viewing the array.
   There are a few functions that can be used to view the array.
   a) array_@ calls the value of a specific element (x,y) in the array
      of the form: x y a1 array_@
   b) SSA. Prints the array to the console in 1 0 format. THis is what the a1 array actually looks like but is harder to view.
      Since SSA shows the value of each element it can also be used to view array b1. This array works behind the scenes and counts up the number of neighbours for each             cell. 
      of the form: a1 SSA
   c) ssa2. Prints the array with X as an alive cell and - as a dead cell. This is much easier to view due to the contrast between the characters. Can only be used with             a1.
      of the form: a1 ssa2
   d) go-stretch. Shows the array as a bitmap with white cells being alive and dead cells being black. This only works for large sizes of n.
      of the form: go-stretch
      
   
3) Running the simulation. There are a few functions that run the simulation:
   a) skipto . use of the form:        no_of_frames a1 skipto
      This will run the simulation for no_of_frames frames and then run a bitmap afterwards to show the new configuation of a1. 
      This is the easiest way to run the simulation
   b) skip . use of the form:        no_of_frames a1 skip
      Runs the simulation for this many frames but doesn't show a bitmap afterwards. a1 can then be shown manually either with ssa2 or go-stretch 
   c) simulate . use of the form:    no_of_frames a1 simulate
      Use for small grid sizes and small number of frames.
      This will print out this many frames to the console. 
   d) nextprint. use of the form:    a1 nextprint
      use this for smaller grid sizes that will fit in the console. It will run the simulation for one frame and then print the values to the console using ssa2.
   e) next1. use of the form:        a1 next1
      Projects a1 forward by one frame according to Life Rules. It doesn't print the new a1. a1 can be printed manually.
   f) next. use of the form:         a1 a2 next
      Applies the rules of Life to a1 and then projects its decision onto a2
   g) counts & decide the slowest way of running it but good for troubleshooting.
      4 arrays, a1 , a2 , b1 , b2 .
      use counts to decide the number of neighbours for each cell in a1 and then save this to b1.
      then use a1 and b1 to decide the cells that live and die with decide, save this to a2.
      Use like this:
      a1 b1 counts
      a1 b1 a2 decide
      a2 b2 counts
      a2 b2 a1 decide
      a1 b1 counts
      a1 b1 a2 decide
      a2 b2 counts
      a2 b2 a1 decide
      etc....
      Can print of any array at any stage in the process for troubleshooting. 
