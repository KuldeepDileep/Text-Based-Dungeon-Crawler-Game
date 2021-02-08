# Text-Based-Dungeon-Crawler-Game
In this assignment you will be creating a text based dungeon crawler game. The functions given here are all that you will need but you can make your own new functions. Details about the assignment are as following:
* The dungeon should not be smaller than 8x8 grid.
* P marks the position of player
* X marks the position of Exit
* E represents enemies on map
* F represents food on map
* T represents trap on map
* H represents health on map
* w represents wall on map
## Dungeon Creation:
You will create a dungeon of size width x height. What this means is that you will need to create a single dimensional dynamic char array of size width x height as given by the user. This should be done inside the CreateDungeon function. You may need to store the starting point and the exit point by using the Point structure. The Traversal function will then use char array to help with the traversing. Here are the guidelines as to how the dungeon should be created:
* You should place walls around the borders of the dungeon
* Traverse the empty spaces one by one and place objects with a 20% probability. If the probability is met then you should generate another random integer. If the value is between 0 and 15, place an enemy. 15 and 30, place health. 30 and 45 place trap. 45 and 60 place food and a wall if it is beyond 60. This will create a dungeon with a reasonable randomness. The numbers can vary if you want to change the difficulty of your dungeon. 
* Now traverse the dungeon again and place the player's starting position at random right next to the left edge of the dungeon. In case you traverse and are unable to place the starting position, place it on the top-left corner by default.
* Place the exit the same way right next to the right edge of the dungeon. Again, if you are unable to place the exit at random, place it at the bottom right corner by default.
## Dungeon Traversal:
Rules for traversing the dungeon are as following:
* You will move left, right, up or down every time
* Each step will consume 1 food
* If you encounter a wall or an edge, you will not move and lose 1 food
* If you reach H, you will gain 1 health.
* If you reach T, you will lose 1 health. You will call the TrapStatements function at this point which will show one of the three random statements.
* If you reach F, you will gain food for 4 to 8 days. You will call the FoodStatements function at this point which will show one of the three random statements.
* If you reach E, you will fight 2 to 4 enemies. You will call the Combat function at this point which will play the combat automatically. In combat you will attack the enemy with a 30% probability to score a hit. If you hot the enemy, You will call the HitStatements function which will show one of the three random statements. The enemies will attack you as well with a 10% probability each for making a hit. If they hit you, you will call the GetHitStatements function which will show one of the three random statements. This will go on till either the enemies die or you die.
* If you reach X, you will win the game
* If you run out of food, you will die
* If you choose 'x' as input for your turn, you will die
