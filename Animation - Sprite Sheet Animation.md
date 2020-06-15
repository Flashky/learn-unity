A sprite sheet animation consist in a big image containing an animation as a sheet.

Somehow it is similar to cartoon animations, as you have multiple images that together give an optical illusion of movement.

## Setting up the animation windows

You will need two windows for doing animations:

- Animation
- Animator

Go to **Window / Animation** in order to add those two windows to the Unity IDE.

## Animating using a sprite sheet animation

You need several things for doing a sprite sheet animation:

1. A **Sliced Sprite Sheet** asset.
2. A **Sprite** Game Object to hold the **Canvas Renderer** and **Animator** components.
3. An **Animation** asset.
4. An **Animator Controller** asset.

Preferably in that order, as you will need the previous thing for configuring the next one:

```
Sprite asset -> Animation asset -> Animator Controller asset -> Game Object with Canvas Renderer and Animator components.
```


### 1. Importing and slicing the sprite sheet

1. Copy your image sprite sheet to the **Sprites** folder.
2. Click on the image.
3. Set **Sprite mode** to **Multiple**.
4. Set **Mesh type** to **Tight**.
5. Click on **Apply**.
6. Click on **Sprite Editor**.

On this new window:

1. Go to **Slice** 
2. Verify that **Type** is set to **Automatic**.
3. Click on **Slice**.
A few rectangles will apear on each sprite sheet image.
4. Click on **Apply**.

After doing this, if you click on your image spreat sheet, you will see there are multiple subimages.

### 2. Creating the Sprite Game Object 

Create a game object with a **Canvas Render** component:

1. Right click on **Hierarchy** pane.
2. Select **2D Object / Sprite**.
3. Add an additional **Animator** component.

Finally, drag one of the sliced sprite sheet sub-images to the Canvas Renderer **Sprite** field.
We will come back here later to configure the Animator.

### 3. Creating the Animation asset

The **Animation** asset will perform the animation using the previously prepared **sliced sprite sheet**.

Easiest way to configure the Animation is the following:

1. Go to the Sprite Sheet asset.
2. Click and select all the sliced images.
3. Right click and select **Create / Animation**.
4. Go to the created animation.
5. Check **Loop Time**.

Now, if you want to see an animation preview, you will need to drag the previously created game object into the preview window.


## 4. Creating the Animator Controller asset

An **Animator Controller** can hold multiple animations, and is responsible of things such as setting the speed and making transitions between animations.

1. Go to the assets.
2. Right click and select **Create / Animator Controller**.
3. Finally, drag your previously created **Animation** asset into the flow diagram.

**Remember:** *You can have multiple animations in your animator controller. It is a good idea togive a generic name to it, for example, Car or CarController, and then the animations might be named after CarTurning, CarBraking, etc...

## 5. Adding the Animator Controller to the Game Object

Finally, go to the game object created at the 2nd step:

1. Add a **Animator** component.
2. Select the previously created **Animator Controller**.

