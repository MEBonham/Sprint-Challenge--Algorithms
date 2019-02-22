Add your answers to the Algorithms exercises here.

Ia) The runtime of this snippet is O(n**3). The actual operation, adding to the total of a, is constant runtime in spite of involving calculation of n**2, but the while loop here is essentially a for loop with an upper bound of n**3. And doing something constant n**3 times is an O(n**3) process.

Ib) I think this is also O(n**3), because there are three nested for loops that have a range dependent on n. These for loops don't run across the whole range of 0 to n -- they start at a value higher than zero, and skip every other index (I think -- modifying your for loop's index value as you go isn't a great idea when avoidable, and I'm not sure exactly how Python handles it) -- but I think that just adds a constant factor to the n**3 determination, which we neglect. The 4th for loop, with a range of k+1 to k+10, will always have 9 iterations (or 4 if it skips every other one), which themselves perform constant-time operations, so this for loop doesn't add an n-dependent number of operations to the total runtime.

Ic) Wow, this is a very inefficient way to multiply by 2! Assuming that "bunnies" is our "n"-variable. This will have a runtime O(n), because it will run one constant operation (adding 2) for each number of bunnies down from the initial input to zero.

II) Putting aside that I'm pretty sure _f_ = 1. Pretending the ground around the building is very soft or something.

This seems to me like a standard binary search of a sorted list; the guarantee in the problem that floors >= f always work one way and that floors < f always work the other way means that the floors are essentially sorted for you already. Start halfway up the building and drop an egg; if it breaks, move halfway down towards the next floor that's been tested and try again. If it doesn't break, move halfway up towards the next floor that's been tested and try again. Eventually you will test two floors next to each other with opposite results; _f_ is the higher of those two floors.

The runtime complexity of this method is O(log n), like a binary search. Because log n could essentially be defined as the number of times you can divide n in two before being left with just one alternative.