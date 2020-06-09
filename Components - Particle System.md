A particle system is useful for doing things like explosion or dust simulation.

Every particle system has two parts:

- Emmiter: Defines the point where the particles will start popping.
- Particles: The particles themself.

## How to create a simple particle system

1. Go to the **Hierarchy**.
2. Right click and select **Effects / Particle System**.

By default, that is enough to create a particle sytem that works.

## Customizing your particle system

Select the game object and go to the **Particle System** component.
Here you have tons of fields that you can configure to customize your particle system to something that matches what you need.

You will notice some fields have a tiny arrow at the right. Those fields values can be set in different ways:

- Constant value.
- Curve value.
- Random value between two constants.
- Random value between two curves.


Let's see some of the configurable values.

### Basic configuration

#### Duration 

Sets how long will the particle system will emmit particles.

#### Looping

When checked, the emission cycle will repeat and never stop.
This might be useful either for debugging purposes or to create permanent emission on particles at any place.

#### Prewarm

*Note: Can only be used if looping is enabled*

Usually, when you start emmiting, you need some time for the particles to spread.
When checked, the initial status will be the same as if an entire cycle would have already run.

#### Start size

It is the size of a single particle in world units.

#### Start lifetime

The start lifetime of the particles of seconds. The particle will die when it reaches zero.

#### Start speed

The start speed of the particles in world units.

#### Start color

The start color of the particles. 
Beside the color, you can also play with the alpha channel to give the particles a bit of transparency.

### Emmision configuration

#### Rate over Time

Sets the number of particles emmited per second.

#### Rate over Distance

Sets the number of particles emmited per distance unit

### Shape

#### Shape

This one is very useful, as it allows us to set the shape the particles will spread: a cone, a box, a rectangle...

#### Position, rotation and scale

These three properties will allow us to change the scale of the emmiting shape and its orientation.


