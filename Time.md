
## Time.deltaTime

Slow computers will compute more frames per second than fast computers.
We want to make our games frame rate independant so the experience is the same in both computers.

The way to do so is using Time.deltaTime

For example, we can adapt the axis movement to the delta time this way:


```C#
void Update()
{
    var deltaX = Input.GetAxis("Horizontal") * Time.deltaTime;
    var newPosX = transform.position.x + deltaX;

    transform.position = new Vector2(newPosX, transform.position.y);
}
```

See also: https://docs.unity3d.com/ScriptReference/Time-deltaTime.html
