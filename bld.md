%title: Solving the Rubik's Cube Blindfolded
%author: @chrishunt
%date: 2014-10-25

TEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEST

---------------------------------------------------------------------

-> @chrishunt <-

---------------------------------------------------------------------

-> # Swap two edges <-

-> R U R' U' R' F R2 U' R' U' R U R' F' <-

---------------------------------------------------------------------

-> # Swap two edges <-

-> `R` U R' U' R' F R2 U' R' U' R U R' F' <-

---------------------------------------------------------------------

-> # Swap two edges <-

-> R `U` R' U' R' F R2 U' R' U' R U R' F' <-

---------------------------------------------------------------------

-> # Swap two edges <-

-> R U `R'` U' R' F R2 U' R' U' R U R' F' <-

---------------------------------------------------------------------

-> # Swap two edges <-

-> R U R' U' R' F `R2` U' R' U' R U R' F' <-

---------------------------------------------------------------------

-> # Solve the corners <-

-> U F R U' R' U' R U R' F' R U R' U' R' F R F' U' <-

---------------------------------------------------------------------

    require 'rubiks_cube'
    
    cube = RubiksCube::Cube.new
    
    cube.solved?
    #=> true
    
    cube.perform! "R2 U2 L' F"

---------------------------------------------------------------------

    solution = RubiksCube::TwoCycleSolution.new(cube)
    puts solution.pretty
    
    > ...
    >
    > Setup:  U' F U
    > Fix:    R U R' U' R' F R2 U' R' U' R U R' F'
    > Undo:   U' F' U
    >
    > Setup:  D' L2
    > Fix:    R U R' U' R' F R2 U' R' U' R U R' F'
    > Undo:   L2 D

---------------------------------------------------------------------
