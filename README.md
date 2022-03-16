# Pizza Delivery Solution

Python solution for [Koneksa coding challenge](https://gist.github.com/mikedelorenzo-koneksa/3d273f862e919782a181c28ef5f50f54) - given a string of cardinal directions and number of delivery persons, return number of unique coordinates visited.

**Part 1 solution (1 delivery person): 2565 houses receive at least one pizza (unittest 1).**

**Part 2 solution (1 delivery person, 1 goat): 2639  houses receive at least one pizza (unittest 2).**

With one delivery person and _two_ goats, 2600 houses will receive at least one pizza.

## Running the file

Run the Solution file to demonstrate, includes unittests.

`python ./Solution.py`

## Method overview

First, we split the dispatch directions for each delivery person into a dict where the keys represent each delivery person (or goat) and the values are the respective directions.

A helper method that 'follows' the dispatch instructions appends each new coordinate for each delivery person to another dict, deliveries{}. 

We are using the 'x' coordinates for each pair to signify the key, and each 'y' value to signify the values for each key. This will allow us to remove duplicates with set() much faster than if we stored each coordinate pair on a one dimensional array, essentially creating our own simple hash table.

Once the dispatch instructions have been fully followed, we then build a set() for each key and add the length of each set, a pythonic way of removing duplicates.

This sum of len(set(key)) produces our final result, the unique list of houses that receive at least one pizza.

## Testing

Inputs in `houses_delivered(directions, deliveryPersons)` are typechecked. To save runtime, checking for suitable characters `^v<>` takes place in `deliver_pizzas`.

## Future implementation possibilities

- Ignore bad input /'clean' bad input
- Graphical visualization (numpy/pandas/seaborn)
- Three dimensional pizza delivery

## Notes

Kept some print() calls commented out for debugging/observation purposes in `split_directions`, `deliver_pizzas`, and `count_unique_coords`
