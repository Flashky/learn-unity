A sprite sheet animation consist in a big image containing an animation as a sheet.

Somehow it is similar to cartoon animations, as you have multiple images that together give an optical illusion of movement.

## Animating using a sprite sheet animation

### Importing and slicing the sprite sheet

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

### Creating the game object

We will need a game object with two components:

- [Sprite Renderer](https://github.com/Flashky/learn-unity/blob/master/Components%20-%20Sprite%20Renderer.md)
- [Animator](https://github.com/Flashky/learn-unity/blob/master/Components%20-%20Animator.md)

We will need also three assets:

- The previously sliced sprite.
- An animation created from the previous sliced sprite
- An animator controller.

