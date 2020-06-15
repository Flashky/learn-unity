A keyframe animation consist on two in a set of images that are manually animated on each frame by moving their positions.

## Setting up the animation windows

You will need two windows for doing animations:

- Animation
- Animator

Go to **Window / Animation** in order to add those two windows to the Unity IDE.

## Animating using keyframe animation

You just need a the following things for doing keyframe animation:

1. A manually sliced **Sprite** asset (it doesn't have to be a sprite sheet).
2. A **Game Object** containing sub-objects each of them with each part of the sliced sprite.
3. An **Animation** asset.
4. An **Animator Controller** asset.

### 1. Importing and slicing the sprite

1. Copy your image sprite sheet to the **Sprites** folder.
2. Click on the image.
3. Set **Sprite mode** to **Multiple**.
4. Click on **Apply**.
5. Click on **Sprite Editor**.

On this new window:

1. Go to **Slice** 
2. Manually slice the parts you need.
3. Click on **Slice**.
A few rectangles will apear on each sprite sheet image.
4. Click on **Apply**.

### 2. Creating the Game Object

1. Create an empty **Game Object**.
2. Add an additional **Animator** component.
3. Drag and drop all the sprite sub-images to the game object.

### 3. Creating the Animation asset and the animator controller

As the game object already contains two sub-images, this way is the faster for creating both the Animation and Animator Controller assets:

1. Click on the **Game Object**.
2. Go to the **Animation window**.
3. Click on **Create**.
4. Give a name to the animation.

Both the Animation and the Animator Controller will be automatically created.

## Recording the animation

Select the **Game Object** and go to the **Animation** pane.

You will see a timeline at the right, there it is where you will create the keyframe animation:

1. Select the part you want to animate.
2. Click on the **Record** button.
3. Click on the left side of the timeline, you will be able to **slide a vertical bar**.
4. Move the bar to a desired point in the timeline.
5. Now move the sprite in the scene to a position.
6. Repeat 2-4 multiple times until you finish. 

This way, you will have a manually created animation in the Unity editor.

You can also change the view to **Curves**, which will allow you to tune the animation in a much more visual way.


