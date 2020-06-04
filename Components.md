## Getting a game object's component

The ``GetComponent<T>()`` method allows to retrieve a component from the current game object.

Example:

```C#
RigidBody2D rigidBody = GetComponent<Rigidbody2D>();
```

## Caching components

Sometimes we might not want be calling the ``GetComponent<T>()`` method constantly.

A way to avoid that is calling the GetComponent method just once at the ``Start()`` method, and then saving it as an attribute.

Example:

```C#
public class Ball : MonoBehaviour
{
    // Cached component
    AudioSource myAudioSource;
    
    // Start is called before the first frame update
    void Start()
    {
        myAudioSource = GetComponent<AudioSource>();
    }
}
```
