# Physics on 2D objects

## Requisites

1. Create a **2D Object Sprite**.

For adding physics we need two different things:

- A Rigidbody which allows the sprite to be simulated by forces.
- A Collider which allows the sprite to collide with other objects.

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
