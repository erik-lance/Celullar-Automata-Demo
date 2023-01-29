# Celullar-Automata-Demo
 Mini async task for CMPLXSY to construct an own CA implementation

#### Model

#### Rules
In this version of Game of Life, similar rules still apply with new additional rules for experimentation with Cellular Automata. Aside from the original two states of live or dead, the patches/cells can also either be male or female cells. This model checks whether the cell is a male or female, and whether their neighbor is a living male or female cell. These cells still interact horizontally, vertically, and diagonally with eight of their neighbors.

With each tick or time step, the following rules are applied:

1. Living cells wtih two or three living neighbors will live and survive.
2. Dead cells with three living neighbors will spawn a new cell, aka that becomes a live cell.
3. Other cells that don't fall into the above rules dies or remain dead.

The rules above were from the original Conway's Game of Life, the rules below are the additional rules that were applied to this model:

4. For any male or female living cell that has atleast one live neighbor of the oposite sex, the original rules can now be applied. As if to ensure that birthing a cell is possible.
5. Any cell that has neighbors with an equal number of male and female living cells will automatically spawn a cell. This is to ensure that creating the next generation is possible.

These rules will continously be applied to create the next generations.
