## Getting a game object from another game object

The ``FindObjectOfType<T>()`` method allows to retrieve a game object.

Example:

```C#
Level level = FindObjectOfType<Level>();
```

If there is more of object, you can also use ``FindObjectsOfType<T>()``.

Example:

```C#
Level[] levels = FindObjectsOfType<Level>();
```

## Caching game objects

Sometimes we might not want be calling the ``FindObjectOfType<T>()`` method constantly.

A way to avoid that is calling the GetComponent method just once at the ``Start()`` method, and then saving it as an attribute.

Example:

```C#
public class Block : MonoBehaviour
{
    // Cached game object
    Level level
    
    // Start is called before the first frame update
    void Start()
    {
        level = FindObjectOfType<Level>();
    }
}
```

## Programatically creating game objects


