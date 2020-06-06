# learn-unity

## Useful links

- [Official documentation](https://docs.unity3d.com/2020.2/Documentation/ScriptReference/)
- [ShareMyGame](https://sharemygame.com/)

## Resources

### Fonts

- [Dafont](https://www.dafont.com/) 

### Sprites and models

- [Kenney](https://kenney.nl/) 

## Managing user input

- [Input](https://docs.unity3d.com/2020.2/Documentation/ScriptReference/Input.html)

## Anchors

Anchors are useful to make a component stay at a certain position regardless the used aspect ratio:

1. Select your component.
2. Click on the anchor square, it has a middle and center words in it.
3. Set the anchor you want to use.
4. Go to **Game** tag.
5. Test different aspect ratios to check that everything is displayed fine under different situations.

## Load a scene from a different scene

Given two scenes, **MenuScene** and **GameScene**, and given a clickable button on MenuScene. If you want to open GameScene when cliking the button, do the following:

1. On MenuScene, right click and **Create Empty** for creating an empty GameObject.
2. **(Optional)** Rename the GameObject.
3. Select the created GameObject.
4. Go to the component **Inspector** and click on **Add Component**.
5. Select script and name it.
6. Add the following method to the class:

```C#
public void LoadNextScene()
{
    int currentSceneIndex = SceneManager.GetActiveScene().buildIndex;
    SceneManager.LoadScene(currentSceneIndex + 1);
}
```

7. Go to build.
8. Add and order all the scenes.
9. Now open the Button component.
10. Go to On Click section at the inspector.
11. Drag the GameComponent to the None box and select the function we created from it.

## Quit game

Just use the following method:

```C#
Application.Quit();
```

Source: https://docs.unity3d.com/ScriptReference/Application.Quit.html
 
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




