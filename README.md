# CameraShakeGodot

![logo_large_color_dark](https://github.com/PepeDux/CameraShakeGodot/assets/108129196/95af0dd8-c6d7-47ce-934c-eb34fd2e9122)

![Static Badge](https://img.shields.io/badge/C%23-purple) ![Static Badge](https://img.shields.io/badge/Godot-white) ![Static Badge](https://img.shields.io/badge/Guide-green)

I would like to contribute to the development of the Godot Engine developer community and that's why I created this guide, I hope it will help you

P.S Criticism and comments are welcome 😄

## Code

```c#
using Godot;
using System;
using System.Threading.Tasks;

public partial class CameraShake : Node
{
    // Export a camera that will shake
    [Export] Camera2D camera;
    Random random = new Random();

    // shakeIntensity - camera shake intensity
    // shakeModifier - camera shake modifier
    // shakeIteration - The number of ticks the camera will shake
    // shakeSpeed - speed between ticks of shaking
    public async Task ShakeAsync(int shakeIntensity = 1, float shakeModifier = 1, int shakeIteration = 10, int shakeSpeed = 10)
    {
        for (int i = 0; i < shakeIteration; i++)
        {
            // Pause between ticks
            await Task.Delay(shakeSpeed);
            // Camera shaking itself
            camera.Offset = new Vector2(
                random.Next(-shakeIntensity, shakeIntensity) * shakeModifier,  // Shaking by X coordinate
                random.Next(-shakeIntensity, shakeIntensity) * shakeModifier); // Shaking by Y coordinate
        }

        // Returning the camera to its initial positions
        camera.Offset = new Vector2(0, 0);
    }
}
```

## About

Camera shake script will help you for project development, camera shake can be used, for example, to increase the impact of gameplay for the player

## How use it

+ Create a CameraShake Script
+ Copy and paste the code
+ Create a CameraShake node
+ Add a camera to the node script
+ Volia!

## Usage example

Example of using the script:

```c#
GetTree().Root.GetNode("GameScene").GetNode<CameraShake>("CameraShake").ShakeAsync(1, 1, 15, 10); 
```

![godot windows opt tools 64_vee8RJ1VD5](https://github.com/PepeDux/CameraShakeGodot/assets/108129196/db9bf011-f02a-4584-af91-e342af35dc03)


## Developer's
[PepeDux](https://github.com/PepeDux)
