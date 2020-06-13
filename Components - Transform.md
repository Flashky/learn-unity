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

### Changing an object position

Just create a new vector with the new coordinates:

```C#
transform.position = new Vector3(0, 25, 10);
```

### Moving an object towards a position

Both ``Vector2`` and ``Vector3`` have the ``MoveTowards`` method that will help us moving an object to the position you want.

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

Example:

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

There is another overriden method for doing this by degrees:

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

