# Physics on 2D objects

## Requisites

1. Create a **2D Object Sprite**.

For adding physics we need three different things:

- A Rigidbody which allows the sprite to be simulated by forces.
- A Collider which allows the sprite to collide with other objects.
- A Physics Material 2D asset which will allow the colliders to apply a behaviour (friction and bounciness) on collision.

## Adding a Rigidbody component

1. Select the sprite and go to the **Inspector**.
2. Click on **Add component**.
3. Select **Rigidbody 2D**.

See also: https://docs.unity3d.com/es/2018.4/Manual/class-Rigidbody2D.html

Now depending on the type of physics we want to apply, we can configure different things at the **Rigidbody 2D** component.

### Body Type

- **Dynamic**: Physics simulation. Gravity and forces affect the object.
- **Kinematic**: Physics simulation. Gravity and other forces **does not** affect the object.
- **Static**: An static object works as if it would have an infinite mass, so it doesn't get affected by anything hitting it.

## Adding a Collider component

1. Select the sprite and go to the **Inspector**.
2. Click on **Add component**.
3. Type **Collider** and select the 2D collider that matches better the shape of the object.

See also: https://docs.unity3d.com/es/2018.4/Manual/Collider2D.html

## Adding a Physics Material

1. Go to the **Assets** folders.
2. (Optional) Create a folder named as **Materials**.
3. Right click on the folder and select Create and then Physics Material 2D.
4. Select the material and adjust **Friction** and **Bounciness** as you wish.
5. Select an sprite having a Collider component.
6. Go to the **Collider** component.
7. Drag the material to the **Material** option.

See also: https://docs.unity3d.com/es/2018.4/Manual/class-PhysicsMaterial2D.html


In summary, an Sprite has a Rigidbody to perform simulations, a Collider to detect collisions with other objects, and a material to determine how the object will bounce after a collision.

## Collision events on a Collider

On an existing object:

1. Select the object and go to the **Inspector**.
2. Click on **Add component** and add a **Box Collider 2D**.
3. Click on **Add component** and add a **script** (only if it doesn't exist already.

Open the script in Visual Studio and do the following:

1. Delete Start and Update methods.
2. Start typing a method named as **OnCollisionEnter2D**, VS will suggest overriding a method.

The previous method will be automatically executed whenever an object having a Collider on it, enters in the space of the trigger collider.

## Collision events on a Trigger

Sometimes we want to trigger some action when an object passes a certain point. 

For example, if a ball hits outside of the gaming zome, we want to score a goal. In an FPS game, we could add triggers when the player enters certain zone to spawn an enemy or boss.

In order to do that, we can create special Colliders which doesn't generate collisions, but trigger events:

1. Create an **Empty** Object.
2. Select the object and go to the **Inspector**.
3. Click on **Add component** and add a **Box Collider 2D**.
4. Select the collider component.
5. Set **Is Trigger** to true.
6. Click on **Add component** and add a **script**.

Open the script in Visual Studio and do the following:

1. Delete Start and Update methods.
2. Start typing a method named as **OnTriggerEnter2D**, VS will suggest overriding a method.

The previous method will be automatically executed whenever an object having a Collider on it, enters in the space of the trigger collider.

## Other events

### Events on mouse click

Colliders also allow us to detect clicks on certain zones.

1. Create an **Empty** object.
2. Select the object and go to the **Inspector**.
3. Click on **Add component** and add a **Box Collider 2D**.
4. Click on **Add component** and add a **script**.

After that, you can add a ``OnMouseDown`` event this way:

```C#
private void OnMouseDown()
{
    Debug.Log("Clicked on Game area!");
}
```

Any time you click in the collider, the previous event will be triggered.

## Global physics

If you want to change the physics to the same for all the rigid bodies on the scene:

1. Click on **Edit...* menu.
2. Select **Project settings...** option.
3. Tune the settings as you wish.

For example, to modify the gravity, set the Y component to the value you need.
The -9.21 value is pretty much the gravity on Earth. 0 means no Gravity at all.

## Layer Collision Matrix

Sometimes you might not want that certain colliders trigger collisions on certain objects.

Unity provides a way to control this easily using layers and a layers collision matrix.

First, we need to create a few layers:

1. Select any game object.
2. Go to the **Inspector**.
3. Go to the **Layer** combobox.
4. Click on **Add layer**.
5. Create as many layers on any of the **User Layer** textboxes as you wish. 

Examples of layers:

- Player
- Enemy
- Player projectiles
- Enemy projectiles.

Now, select any game objects with colliders and assign them to the layer you want.
Finally, let's configure the layer collision matrix:

1. Go to **Edit / Project Settings...**.
2. Go to **Physics 2D**.
3. You will find the **Layer Collision Matrix** at the bottom:
  3.1. By default, everything is checked.
  3.2. Uncheck any layers you don't want to collide between them. 
     
### Example:

- **Given:** a coop shooting game. 
- **When:** either friends and foes can pass through between them without blocking.
- **And:** there is no friendly fire.

Then, for handling collisions you would create four layers:

- Friend
- Foe
- Friendly Fire
- Foe Fire

And you will assign the following values to the collision matrix:

|        | Friend | Foe | Friendly Fire | Foe Fire |
|--------|--------|-----|---------------|----------|
| Friend |        |     |               | x        |
| Foe    |        |     | x             |          |
