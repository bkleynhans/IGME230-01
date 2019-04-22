# Project 3 - Sprite-based Game or Experience (Roof Breaker - The Breakout Adaptation Using Physics)
## Summary
Roof Breaker is a clone of the original Arkanoid released by Taito in 1986.  The overall look is similar and the maps are the same maps, but the actual implementation of the paddle is different.  In the original Arkanoid the ball was reflected outward from the center of the paddle.  The closer you are to the edge of the paddle, the greater the angle of reflection.  I attempted to expand on the idea by implementing angular vector and physics calculations to determine angle of reflection based on angle of entry and velocity of both paddle and projectile.  You thus change direction of the projectile based on the velocity (speed and direction) at which you impact the projectiles.

This new spin on an old classic should bring multiple hours of entertainment.

# Table of Contents
=================

<!--ts-->
* [Project 3 - Sprite-based Game or Experience (Roof Breaker - The Breakout Adaptation Using Physics)](#project-3-roof-breaker)
	* [Summary](#summary)
* [Table of Contents](#table-of-contents)
* [Proposal](#proposal)
	* [High Concept](#high-concept)
	* [Premise](#premise)
* [Final Product](#final-product)
	* [Detailed Overview](#detailed-overview)
		* [How To](#how-to)
		* [Game Layout](#game-layout)
	* [Technical Implementation](#technical-implementation)
		* [Loading Data](#loading-data)
		* [Gameplay](#gameplay)
		* [Difficulties](#difficulties)
	* [About The Developer](#about-the-developer)
* [Documentation](#documentation)       
	* [Resources Used](#resources-used)
	* [Project Requirements Met](#project-requirements-met)
		* [Functionality](#functionality)
		* [Design and Interaction](#design-and-interaction)
		* [Media](#media)
		* [HTML CSS](#html-css)
		* [Code Conventions](#code-conventions)
* [Grade](#grade)
<!--te-->

# Proposal
## High Concept
Create a JavaScript-driven game using PixiJS.

## Premise
The idea was to create a game or experience that would meet the requirements of the assignment.  I am however not a very creative individual and was wondering for weeks (since project 1 was assigned) about what I could do.  Even though I am not a very originally creative person I have a very good nack for replication.  My creativity is around solving problems, not making something new and that is when I made the final decision to create a derivative of the classic Arkanoid game.

My project is therefore a recreation of Arkanoid.  I would implement the paddle and projectile movements as well as powerups and multiple levels.  This would require multiple sprites and sounds and I would also try to implement physics based movement.  The score would be accumulated through destroying bricks and collecting drops that provide additional points.  Lives will be implemented using the three-heart system.

# Final Product
## Detailed Overview
### How To
The goal of the game is to keep the projectile from leaving the bottom of the screen through all the levels.  If this is achieved the game is won.  To achieve this the player moves a paddle from side to side to "bounce" the projectile back at the blocks on the screen.  Powerups are collected to improve/decrease success chances.  The player starts with three lives which are lost, one by one, if the projectile leaves the game scene.

### Game Layout
The player starts with a stationary paddle in the bottom center of the screen.  Moving the mouse displays a "projection" of the ball path, but the paddle itself cannot be moved.  The player left-clicks anywhere in the play field which would launch the projectile and release the paddle, allowing movement.

Throughout the game multiple powerups will be released when blocks are destroyed, the player can choose to collect these.  If however the player opts for a powerup instead of the ball, a life is lost.  If all three lives are lost, the game is over.  There are however additional lives that can be collected from the random powerups.  Once all blocks on a scene have been destroyed, the game advances to the next level.

## Technical Implementation
### Loading Data
All the data associated with the blocks, projectile, powerups and levels are contained in JSON files.  When the start scene is displayed, these datasets are created and the JSON files are loaded.  The sound and sprite files are also loaded for easy access during gameplay.

### Gameplay
Each level is loaded from the level JSON file.  Depending on the numbers defining the levels different types of tiles are loaded for the level.  The numbers supplied in the levels JSON file relate to a translator function in utilities.js, which contains information about strength, color and type of block.  This information is used to extract the corresponding image data from the breakout_tile_free.json file.  The path to the sprite that is associated with the properties from the level file is then extracted to place the appropriate sprite in the appropriate location in the game scene.  During level creation a randomization algoritm runs and assigns powerups to the blocks.  The numbers of powerups and the blocks to which they are assigned are completely random.  There are multiple sounds implemented to indicate different actions as well as warning sounds and screen flashing to indicate when powerups are nearing their end.

### Difficulties
The biggest (and most difficult) change I made was relating to the reflection of the projectile off of the paddle.  Traditionally the paddle was divided into two 90 degree sections, one on the left and one one the right.  When taking the two 90 degree sections and dividing them into degrees (both sides from 0 to 90), the paddle would reflect the ball at an angle that is related to the position on the paddle, not the angle of impact.  This means that regardless of which angle the ball approached the paddle from, if it hit the paddle half way from the side to the center, it would be reflected at 45 degrees relative to the paddle.

The new reflection works by calculating the entry velocity of the projectile as well as the speed of the paddle.  Using Newtonian physics we then calculate the exit angle and direction of the projectile.  You can thus redirect the projectile in any direction if you can estimate the correct velocity at which to het the projectile.

There is a start scene, game scene and game over scene.

## About The Developer
Benjamin Kleynhans is doing his Game Design and Development major. While design is part of the major, it is not something that he wants to do. He is a programmer at heart and is more than happy making someone elses vision a reality.

To learn more about Benjamin, click on [About Benjamin Kleynhans](https://people.rit.edu/bxk8027/230/index.html "Site Home") to be directed to his homepage.

# Documentation
## Resources Used
Multiple different resources were used including:

[Imagine Labs](http://www.imaginelabs.rocks/?product=breakout-brick-breaker-game-tile-set-free "Imagine Labs")
[Mozilla Developer Network](https://developer.mozilla.org "Mozilla Developer Network")
[Stack Overflow](https://stackoverflow.com "Stack Overflow")
[Tutorials Point](https://tutorialspoint.com "Tutorials Point")
[W3Schools](https://www.w3schools.com "W3Schools")
[ZapSplat](https://www.zapsplat.com "ZapSplat")

## Project Requirements Met
### Functionality
- Used PixiJS
- It is a game, so it is as useful as a game can be
- Uses AABB collision detection.  Expands on AABB to determine which side of the collision occurred on and implements forces using normalized vector math and linear momentum.
- There are no JavaScript errors
- Uses two JSON files to read and parse data relating to the sprites which are implemented and changed based on interaction in game.

### Design and Interaction
- Please retro graphic design following Arkanoid themes
- Everthing is well labeled
- No instructions are required, the game was designed in such a way that anyone should figure it out after the first or second play.  A user cannot generate an error in the game as the user doesn't provide any input other than mouse movement and left-click to fire the first projectile
- It works well on any screen that can support 800x600 or higher resolutions.

### Media
- In the breakout directory there are 64 images that were acquired from ImagineLabs under the Creative Commons Zero license.  This license allows the re-use of the images without attribution, but the included license file states "without alteration".  Since I'm not a legal expert and the images (though they are large when opened as images) are already web optimized I opted not to resize them.  The 64 images are less than 1 Mb all together.
- There is sound.
- Fonts, graphics, spritesheets and sounds have all been replaced.

### HTML CSS
- The page passes HTML5 validation without errors.
- The page passes CSS validation without errors.
- There are only three properties that are changed with CSS therefore I don't believe it justifies having it's own file.  These three lines are in the game.html file.
- There is no HTML other than the skeleton for the file, hence there are no semantic styles used.  The entire HTML file, including definitions, imports and styles is only 32 lines of code.

### Code Conventions
- No vars are used.
- There was no dom traversal outside of PixiJS hence no selectors were used.
- There are only two blocks of code (2 function calls of about 20 lines) that are similar (not the same), but they cannot be seperated from the functions where they are located because they cross reference other local variables.  The one also uses calculations as part of the input conditions to the function call while the other does not.
- The entire program consists of 6 files
	- 3x JavaScript
	- 2x JSON
	- 1x HTML
- All variable and function names begin with a lower case letter.
- All code is well commented
- All console.log() calls are commented

# Grade
I believe I deserve full credit (and extra credit if available) for this project.  I spent more than 60 hours working on this project to ensure everything works well.
