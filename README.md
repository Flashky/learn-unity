# learn-unity

## Useful links

- [Official documentation](https://docs.unity3d.com/2020.2/Documentation/ScriptReference/)
- [ShareMyGame](https://sharemygame.com/)


## Managing user input

- [Input](https://docs.unity3d.com/2020.2/Documentation/ScriptReference/Input.html)

## Anchors

Anchors are useful to make a component stay at a certain position regardless the used aspect ratio:

1. Select your component.
2. Click on the anchor square, it has a middle and center words in it.
3. Set the anchor you want to use.
4. Go to **Game** tag.
5. Test different aspect ratios to check that everything is displayed fine under different situations.


## Tips & Tricks

### Make your camera to fill the Canvas

1. Make sure Camera component is not a child of Canvas component.
2. Select Canvas.
3. Set **Render Mode** to **Screen Space - Camera"".
4. Set **Render Camera** to the camera you want to fit into the Canvas.

Source: https://stackoverflow.com/questions/33086715/match-canvas-with-main-camera-unity

### Make your main Canvas to scale with screen resolution

1. Select Canvas.
2. Set **UI Scale Mode** to **Scale With Screen Size**.
3. Set **Reference Resolution** to **1920x1080**.
4. Go to **Game** tab.
5. Set the aspect ratio to **16:9**.




