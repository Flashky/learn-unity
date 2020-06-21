
## Input.KeyDown

```C#
Input.GetKeyDown(KeyCode);
```

## Input Manager

In **Edit / Project Settings... / Input Manager** you will have certain predefined input axes and buttons.

For example:

- "Horizontal" axe has a negative button "left", and a positive button "right". Everything is configurable over there.
- "Fire1" button has a negative button "left", and a positive button "right". Everything is configurable over there.

There are certains functions in the Input API which allows to directly uses these predefined controls.

### Input.GetAxis(string axisName)

 The ``Input.getAxis(axisName)`` method allows as to obtain input from axis such as "Horizontal" or "Vertical".

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

### Input.GetButtonDown(String buttonName)

The ``Input.getButtonDown(axisName)`` method allows us to obtain input from predefined button configurations such as "Fire1" or "Fire2".

For example, to use the "Fire1" configuration:


### Input.mousePosition

The ``Input.mousePosition`` property returns you the position of the mouse at the very moment you call the method.

This property has two coordinates:

- Input.mousePosition.x
- Input.mousePosition.y


