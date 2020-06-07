

## Creating asset menus

Adding ``CreateAssetMenu(menuName = "A menu option name")]`` will make the asset available as an option at the menu when creating objects:

Example:

```C#
[CreateAssetMenu(menuName = "Enemy Wave Config")]
public class WaveConfig : ScriptableObject
{
 // Your class content here
}
```
