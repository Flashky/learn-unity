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

## Trigger Colliders

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




