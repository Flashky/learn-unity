
## KeyDown

```C#
Input.GetKeyDown(KeyCode);
```

## GetAxis

In **Edit / Project Settings... / Input Manager** you will have certain predefined input axes.
For example "Horizontal" axe has a negative button "left", and a positive button "right". Everything is configurable over there.

To detect a certain Input using the axe configuration, just use the ``Input.getAxis(axisName)`` method.

For example, to use the "Horizontal" axe:

```C#
void Update()
{
    float deltaX = Input.GetAxis("Horizontal");
    float newPosX = transform.position.x + deltaX;
    transform.position = new Vector2(newPosX, transform.position.y);
}
```

This will update the horizontal position of the object each time we press the left/a, right/d keys.
