# Celullar-Automata-Demo
 Mini async task for CMPLXSY to construct our own CA implementation

## Model
Our cellular automata is based off of Conway's game of life with some of our own adjustments. It was made in NetLogo. 

Originally we constructed it by simply mimicking the rules seen in the game of life ending up with the below model:

<img src="https://github.com/erik-lance/Celullar-Automata-Demo/blob/master/img/ca_ver_1.gif" width=50% height=50%>

Afterwards, to study more on Cellular Automata, we decided to try experimenting as well by implementing a distinguishing factor amongst the cells which is their sex. It is going to change how the cells interact both on how they increase and decrease. Below is how the final model looks like.

<img src="https://github.com/erik-lance/Celullar-Automata-Demo/blob/master/img/ca_ver_2.gif" width=50% height=50%>

We wanted to simulate how reproduction may work with two different sexes that need each other to reproduce unlike the original game of life where the cells are sexless. In turn, our model didn't reduce in size, rather it increased because of reproduction.

We recommend using a starting-density of 8 to see the model in action clearly. With a tick speed 35% of the tick bar.

There are 3 cell types. We have a dead/empty cell which is white, blue for a male cell, and pink for a female cell. The patches interact based on 5 variables which are

```
patches-own
[
  live?
  live_neighbors
  female?
  live_female
  live_male
]
```

Where `live?` checks if the cell is living, `live_neighbors` checks for neighbors that are still living, `female?` checks if cell is a female, and the `live_female`, `live_male` variables simply check the number of live female/male cells in their vicinity.

After completing this task, we realized that the Cellular Automata we created takes up more space in a grid than it would originally. This may be due to the distinction of cell gender allow more space being taken in the grid.

## Rules
In this version of Game of Life, similar rules still apply with new additional rules for experimentation with Cellular Automata. Aside from the original two states of live or dead, the patches/cells can also either be male or female cells. This model checks whether the cell is a male or female, and whether their neighbor is a living male or female cell. These cells still interact horizontally, vertically, and diagonally with eight of their neighbors.

With each tick or time step, the following rules are applied:

1. Living cells wtih two or three living neighbors will live and survive.
2. Dead cells with three living neighbors will spawn a new cell, aka that becomes a live cell.
3. Other cells that don't fall into the above rules dies or remain dead.

The rules above were from the original Conway's Game of Life, the rules below are the additional rules that were applied to this model:

4. For any male or female living cell that has atleast one live neighbor of the oposite sex, the original rules can now be applied. As if to ensure that birthing a cell is possible.
5. Any cell that has neighbors with an equal number of male and female living cells will automatically spawn a cell. This is to ensure that creating the next generation is possible.

These rules will continously be applied to create the next generations.
