The **Image** component allow us to add images to a canvas.

## Create an Image component

1. Go to the **hierarchy**.
2. Select **UI / Image**.
3. Drag any image you want to use to the **Source Image** attribute.

## What is the difference to drag and drop an image?

When you drag and drop an image, it will create a game object with a **Sprite Renderer** component.
On the other side, when you create an **Image**, it will create a game object with two components: **Canvas Renderer** and **Image**.

A **Sprite Renderer** fits better for creating sprite objects: anything that decorates your game. An **Image** fits better for backgrounds such as:

- Splash Screens.
- Main menus.
- Static backgrounds.

## Important attributes

#### Source Image

Contains the image the component will use.

#### Preserve Aspect

The image will preserve its aspect ratio.

#### Set Native Size

The image will fill the entire canvas.




