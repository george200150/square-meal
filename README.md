# square-meal
javascript phaser 3 game


Controls:
player1 a.k.a. "dude" (purple + yellow) a.k.a. "home": ARROW KEYS + SHIFT
player2 a.k.a. "villain" (blue + red) a.k.a. "away": WASD + SPACE

Scoring:
1 apple = 1 point
1 kill enemy = 10 points

Bricks:
WALL: cannot pass through it, just the world frame.
STEEL: can be picked up, can be pushed, has high drag and slows down fast when thrown.
WOOD: can be picked up, can be pushed, has low drag and keeps its momentum pretty well.


How to play:
	- The two players start in diagonally opposite corners of the map.
	- They have to collect apples and fight each other in order to win.
	- To collect apples, they have to touch the apples then they are immediatelly picked up. After every two apples picked up, the game generates two new apples.
The generation of the apples depends on the position of the player that picks up every second apple (i.e. if in left half of the map, the next two apples generates on the right side of the map). This information could be used to adjust playstyle accordingly.
	- Every player has one inventory slot. When that slot is empty, when the player touches a brick, it automatically picks it up. If the inventory is full, the player will bump into bricks and start pushing them.
	- Players can throw the bricks that they have in their inventory. When pressing the attack button (i.e. SPACE or SHIFT), they will throw the brick in their inventory in the direction they were facing. If the inventory is empty, nothing happens.
	- Thrown bricks will slide along the map. They bump into other bricks and they make them move too, meaning that all the colliding bricks can hurt you. Bricks ignore apples, they do not interact in any way with them. When a moving brick hits a player, they will immediately die and respawn on their starting point. Moving bricks can collide with other thrown bricks which make it possible to dodge an attack by throwing a brick in the other's incoming direction in order to cancel out the forces.
	- Every moving brick that hits a player will disappear together with any brick the hit player had in their inventory at the moment of the collision. The game ends when there are no more bricks on the map or in the inventory of the players. The player with the most points is declared a winner.
	- Bricks can be piled up with no problem whatsoever. It looks weird.
	- Throwing a brick that collides with another brick will immediately make it come to a standstill.
	- Players do not collide with each other.


FUTURE UPDATES TODO:
	- make bricks not able to be placed on outside walls or on other bricks
	- find out why bricks pile up when pushed
	- multiplayer via sockets