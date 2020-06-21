Obtaining the main camera

Camera.main


### Camera.main.ScreenToWorldPoint(Vector2)

Converts the given screen pixel coordinates to world units.

Example, converting a mouse click to the closest world unit:

```c#
private void OnMouseDown() {
  Vector2 clickPos = new Vector2(Input.mousePosition.x, Input.mousePosition.y);
  Vector2 worldPos = Camera.mainScreenToWorldPoint(clickPos);
  
  // worldPos will contain the relative world unit to clickPos.
  
}
```
