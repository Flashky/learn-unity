To restrict an object from moving out of the camera, we can use Math.Clamp function

This function receives three parameters:

- The given position.
- The minimum value for the position.
- Tha maximum value for the position.

It returns a float that will be:
- The given position if it is between min and max value
- The minimum position if the position is less than min value.
- The maximum position if the position is greater than the max value.

So, for using it, we would calculate a coordinate:


```C#

// Given this value
float xValue = 23f;

// Clamp it to validate it doesn't gets outside the min and max value:
float xPos = Mathf.Clamp(xValue, xMin, xMax);

// Finally apply the transformation:
transform.position = new Vector3(xPos, 0f, 0f);

```

See also: https://docs.unity3d.com/ScriptReference/Mathf.Clamp.html

