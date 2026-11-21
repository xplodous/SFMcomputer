REQUIRED MODS:

	https://www.curseforge.com/minecraft/mc-mods/super-factory-manager-unofficial-backport-sfm-ub
	https://www.curseforge.com/minecraft/mc-mods/storage-drawers
	https://www.curseforge.com/minecraft/mc-mods/dank-storage

SETUP:

By default, SFM code can only be run once per second. In order to fix this, set the config "timerTriggerMinimumIntervalInTicks" to 1.

The memory is composed of modules that communicate with each other. For a module, place 3 scripted managers on the same inventory cable network. Put 3 Dank 7s on the network, labelled "B", "D", and "N", and place a creative vending drawer on the network, labelled S. Each module's "N" dank will be the next module's "B". Make sure each network can only see its Dank 7s and not any others.

The program is set up identical to the memory.

B -> [N/B] -> [N/B] -> [N/B] -> N

For the ALU, connect one manager to a dank 7 labelled "B" and a creative vending drawer labelled "S".

The CPU must be connected to 7 things:
- The ALU's dank 7, labelled "ALU"
- The first RAM module's B, labelled "RAM"
- The first Program module's B, labelled "P"
- A creative vending drawer, labelled "S"
- A dank 7 labelled "B"
- A creative drawer (NOT vending) labelled "PC"
- Redstone signal to the manager (User input)


NOTES:

- Division is done at one item per tick: therefore, large numbers take a long time to calculate. A fix is planned to partially alleviate this
- A screen was originally planned, but scrapped due to a factor called "needing to build it in-game"
- Non-positive or non-integer numbers are not planned


INSTRUCTIONS:

0: HALT

	Stops the program

1: ADD(a,b,r)

	Writes the sum of index a and index b into index r

2: DIFF(a,b,r)

	Writes the difference of index a and index b into index r

3: MULT(a,b,r)

	Writes the product of index a and index b into index r

4: DIV(a,b,r)

	Writes the truncated quotient of index a and index b into index r

5: JMPTO(i)

	Jump program counter to i

6: JMPC(i,b)

	Jump program counter to i if index b=0

7: SET(i,a)

	Set index i to value a

8: INC(i)

	Increment the value at index i

9: DEC(i)

	Decrement the value at index i

10: WAIT

	Wait until redstone signal

11: COPY(a,b)

	Copy a value from index a to index b

12: INPUT(i)

	Wait until redstone signal, then put the value from B slot 3 into index i

64: ERROR

	Set state to 404. Effectively halts the program