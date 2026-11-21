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

The CPU must be connected to 6 things:
- The ALU's dank 7, labelled "ALU"
- The first RAM module's B, labelled "RAM"
- The first Program module's B, labelled "P"
- A creative vending drawer, labelled "S"
- A dank 7 labelled "B"
- A creative drawer (NOT vending) labelled "PC"
