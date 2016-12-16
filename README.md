This project shows how to export 4K resolution 360 Videos and Photos from inside of Three.js scenes.

The process is [described in this blog post](https://medium.com/p/788226f2c75f)

# Examples

[example 4k video from demo scene on YouTube ](https://www.youtube.com/watch?v=nsJS0_vms5c)

![Alt text](screencap2.jpg?raw=true "Inside of a 3D environment")

[example 4k test video on YouTube ](https://www.youtube.com/watch?v=GcY7f8EYEQg)

![Alt text](screencap.jpg?raw=true "Early Tests")

# How this works
Basically you take a cube camera, save it to equirectangular photo, and then stitch those together to make a video.  Add some metadata and voila! You can then post them to Facebook and Youtube.

I made some modifications to the [CCapture.js library](https://github.com/spite/ccapture.js/), where I added a CC360Encoder class that calls into an cubemap to equirectangular image capture library [from the same author](https://github.com/spite/THREE.CubemapToEquirectangular). I made modifications to that library also, where I prepare the cube camera data for the encoder with the preBlob class.  Finally, I was running into memory issues very quickly, so I re-implemented batching in CCapture.js for the equirectangular .jpg sequences.

It will capture a batch every N seconds according to the a

# Try Online

[demo scene](https://www.youtube.com/watch?v=nsJS0_vms5c)

[simple tests](https://www.youtube.com/watch?v=nsJS0_vms5c)


# Setup

Clone the repository and serve its files using a webserver of your choice.

index.html contains simple test shapes.  moving the camera during capture has no effect.

demo.html is hacked into a three.js demo scene.  moving the camera during capture will change the final shot.