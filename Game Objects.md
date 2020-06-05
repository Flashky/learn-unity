## What is a game object

A game object is anything that is part of a scene. 

In other words, anything that appears under the hierarchy tree.
Game objects may or not have components of any type: colliders, rigid bodies, scripts, audio sources...

## Manually instantiating game objects

### Through hierarchy

Right click on the hierarchy pane and select the type of object you want to create.
You can even create empty objects, which are useful for packing other game objects together or for adding just scripts.

### Through assets

You can drag mostly any asset (images, audio files, prefabs...) into either the game scene or the hierarchy tree. 
When do so, they will be automatically added as game objects.

## Programatically instantiating game objects


See also: https://docs.unity3d.com/ScriptReference/Object.Instantiate.html

## Retrieving game objects

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


