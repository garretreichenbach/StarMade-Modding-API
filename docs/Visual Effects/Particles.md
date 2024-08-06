# Particle System
## Vanilla Particle System
As you may have noticed, StarMade does not actually utilize many particles in-game. While there is a rudimentary particle framework in place, it is unfinished 
and unintuitive. This is why StarLoader has its own particle system, which is much more robust and user-friendly.
## StarLoader Particle System
The ModParticle system is designed for mods to easily make particles. Making a new particle through this system requires defining only two objects:
* 'ModParticle' - Controls the behavior of the particle.
* 'Sprite' - The sprite that the particle will use.
### ModParticle
The ModParticle class is the main class that controls the behavior of the particle. It has the following fields:
* `particleSpriteId` The particle sprite id (more on this later).
* `colorR, colorG, colorB, colorA` Byte values (127 max) of the particle's color.
* `lifetimeMs` How many ms the particle lives before deletion.
* `cameraDistance` Used to sort particles, should never need to be changed.
* `startTime` When the particle came into existence.
* `position` The particle's position in the world.
* `rotation` The particle's rotation.
* `sizeX, sizeY` The size of the particle.
* `velocity` How much the particle moves each tick.
* `normalOverride` Particle alignment (more on this later).