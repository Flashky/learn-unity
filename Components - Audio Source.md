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

## Play sound with no interruptions

The previous method stops to play whenever a second play call is done.
The ``PlayOneShot`` method allows to play the sound in all its length, however, its need an AudioClip as a parameter:

```C#
private void OnCollisionEnter2D(Collision2D collision)
{ 
  AudioSource audioSource = GetComponent<AudioSource>();
  audioSource.PlayOneShot(audioSource.clip);
}
```

## Official documentation

- [Audio files - Supported formats](https://docs.unity3d.com/Manual/AudioFiles.html)
- [Audio Source](https://docs.unity3d.com/Manual/class-AudioSource.html)
- [Audio Clip](https://docs.unity3d.com/Manual/class-AudioClip.html)
