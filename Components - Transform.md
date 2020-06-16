The **Transform** component allows us to control three parameters of the objects:

- Position
- Rotation
- Scale

Every game object (even the empty ones) have a Transform component by default.

## Accesing the Transform component

Mst components need ``GetComponent<Type>()`` to be retrieved.

However, the Transform object can be directly accesed using either ``gameObject.transform`` or just ``transform``.

## Position

Position controls where in the screen is an object located in world units.

There are multiple ways to change the position of an object.

### Changing the position of an object just using a vector

The simplest way to changing an object position is by changing directly the transform position coordinates.

Just create a new vector with the new coordinates:

```C#
transform.position = new Vector3(0, 25, 10);
```

You can add vectors directly, for example, if you want to move a little to the left on each Update:

```C#
transform.position += new Vector2(-1, 0);
```

:bulb: **Did you know...?**

...there are some predefined vectors to move to certain fixed positions such as left, right, top and bottom.

They are just shorthands for (-1,0), (1,0), (0,1), 0,-1).

The previous example can be then rewritten to this:

```c#
transform.position += Vector2.left;
```

### Moving an object using Tranform.Translate

This one is initially pretty similar to the previous one:

```C#
transform.Translate(new Vector3(0, 25, 10));
```

So, what is the difference?

The default method with just the vector is not different to using transform.position. However Translate has other overriden methods that allows to move objects relative to a space or local position.



### Moving an object using Vector2.MoveTowards

Sometimes we know exactly the exact coordinates we want an object to move, and we also know the movement speed of the object.
In that case, both ``Vector2`` and ``Vector3`` have the ``MoveTowards`` method that will help us moving an object to the position you want frame by frame

Example:

```C#

public class Movement : MonoBehaviour
{
    // On this example, modify Vector2 to select a position you want to move the object.
    [SerializeField] Vector2 targetPosition;
    [SerializeField] flot moveSpeedByFrame = 2f;
    
    // Update is called once per frame
    void Update()
    {
        var movementThisFrame = moveSpeedByFrame * Time.deltaTime; // Frame rate independant
        transform.position = Vector2.MoveTowards(transform.position, targetPosition, movementThisFrame);

    }
}
```



## Rotation

As its name suggests, it controls the rotation of the object.

### Rotate an object

The ``Transform`` class has a ``Rotate`` method that allows us to rotate the game object by the amount specified by a Vector3.

This method has multiple ovrrides

#### Transform.Rotate(Vector3 eulers)

This one rotates using a Vector3.

```C#
public class Spinner : MonoBehaviour
{

    [SerializeField] float rotationSpeed = 0.5f;

    Vector3 angularRotation;

    private void Start()
    {
        angularRotation = new Vector3(0, 0, rotationSpeed * Time.deltaTime);
    }

    // Update is called once per frame
    void Update()
    {
        transform.Rotate(angularRotation);
    }
}
```

#### Transform.Rotate(float xAngle, float yAngle, float zAngle)

This one rotates using degrees. 

```C#
public class Spinner : MonoBehaviour
{

    [SerializeField] float rotationSpeed = 360f;

    // Update is called once per frame
    void Update()
    {
        transform.Rotate(0,0, rotationSpeed * Time.deltaTime);
    }
}
```

