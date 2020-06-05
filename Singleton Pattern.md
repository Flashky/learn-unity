When loading a new scene, any object from the previous scene is deleted.

However, sometimes we want to keep a single instance alive and being the same for all the scenes (for example a scoreboard). A way to achieve this is by using the Singleton Pattern.

Here is a way to do it:

```C#
public class GameSession : MonoBehaviour
{
    // Awake is the first method called at the object lifecycle
    private void Awake()
    {

        // Singleton pattern to ensure a single GameStatus in all the game duration
        int instances = FindObjectsOfType<GameSession>().Length;

        if(instances > 1)
        {
            gameObject.SetActive(false); // Avoids any unexpected behaviour before destroying the game object
            Destroy(gameObject);
        } else
        {
            DontDestroyOnLoad(gameObject);
        }

    }

    // This is not part of the Singleton pattern.
    // But it will allow us to reset any data stored in this object in case of need.
    public void ResetGame()
    {
        Destroy(gameObject);
    }
}
```
