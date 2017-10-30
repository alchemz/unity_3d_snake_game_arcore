# unity_3d_snake_game_arcore

## Steps
1. Create the snake head prefab, and tag it as the player
2. Create the SnakeMovement.cs to enable the mouse control
- Inside the SnakeMovement.cs, create MoveForward(), Rotation() methods.
- Add a method CameraFollow() to make the camera follow the movement, find the GameObject with tag "MainCamera"
- Use Vecotor3.SmoothDamp to make the transform smooth
