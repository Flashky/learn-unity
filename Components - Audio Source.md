## Adding audio assets

1. Create a folder and name it as **Audio**.
2. Copy your audio clips to that folder.

## Creating the component

1. Select a game object and go to the **Inspector**.
2. Click on **Add component**.
3. Select **Audio Source**.
4. Go to your **Audio** assets folder.
5. Drag the audio asset you want into the **AudioClip** property.
6. Uncheck **Play On Awake** property.

## Playing a sound on collision

### Requisites

Have a game object with two components:
- Collider component.
- Script component.

### Play sound

```C#
private void OnCollisionEnter2D(Collision2D collision)
{
    GetComponent<AudioSource>().Play();
}
 ```

### Play sound with no interruptions

The previous method stops to play whenever a second play call is done.
The ``PlayOneShot`` method allows to play the sound in all its length, however, its need an AudioClip as a parameter:

```C#
private void OnCollisionEnter2D(Collision2D collision)
{ 
  AudioSource audioSource = GetComponent<AudioSource>();
  audioSource.PlayOneShot(audioSource.clip);
}
```

### Play a sound on a certain point

For this case in particular, we can play a sound even with no AudioSource component.

When you use the ``Destroy(...)`` method, any component will be destroyed, including Audio sources, so we won't be able to play any sound.

However, there is a way to play a sound at a certain point using ``AudioSource.PlayClipAtPoint(AudioClip, Vector3)``.

Example:

```C#
public class Block : MonoBehaviour
{
    [SerializeField] AudioClip breakSound;

    private void OnCollisionEnter2D(Collision2D collision)
    {
        AudioSource.PlayClipAtPoint(breakSound, Camera.main.transform.position);
        Destroy(gameObject);
    }
}
```

In the previous case, an AudioClip field was added to select the clip to be played. Then, on a collision, the sound is played and at the same time, the game object is destroyed.


## Official documentation

- [Audio files - Supported formats](https://docs.unity3d.com/Manual/AudioFiles.html)
- [Audio Source](https://docs.unity3d.com/Manual/class-AudioSource.html)
- [Audio Clip](https://docs.unity3d.com/Manual/class-AudioClip.html)
