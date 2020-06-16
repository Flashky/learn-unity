The **Animation** asset contains information about a certain animation.


## Adding an animation event

Animation events are points at the animation which trigger any C# function you set.

To add an animation event:

1. Select the **Animation** asset you want to modify.
2. Open the **Animation window**.
3. Click on the **Add event...** button.

Now the **Inspector** will open:

1. Set function name at the **Function** field.
2. Set the float/int/string/object parameter you want.

Finally, you must go to the related C# script (the one that is at the same game object as the sprite renderer), and implement the function.

You can have multiple animation events.
