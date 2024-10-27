# Tutorial for Virtual Reality Artwork: "World-Building and Futurism"

##TABLE OF CONTENTS
[Step 1: Create a workspace in Codecademy](#Step 1: Create a workspace in Codecademy)


## Step 1: Create a workspace in Codecademy

- Log in to your Codecademy account
- Click Workspaces > Add workspace > HTML/CSS/JS
- Add a title to your workspace

## Step 2: Copy the template code below to your workspace's index file

```html
<html>

<head>
<!-- The next two lines of code are the A-Frame libraries -->
<script src="https://aframe.io/releases/1.6.0/aframe.min.js"></script>
<script src="https://unpkg.com/aframe-environment-component/dist/aframe-environment-component.min.js"></script>
</head>

<body>

<!-- add your scene environment and objects below -->
</body>

</html>
```

## Step 3: Add an empty scene, a camera and a cursor

- Paste the following code between the `<body></body>` tags

```html
<a-scene id="myScene">
  <a-camera> <a-cursor></a-cursor> </a-camera>

</a-scene>
```

## Step 4: Create a preset or custom environment that sets a futuristic mood
### Create a preset environment

- Paste the following code between the `<scene></scene>` tags

```html
<a-entity environment="preset: tron; dressingAmount:500"></a-entity>
```

- Change the preset environment by choosing from the following list:
default, contact, egypt, checkerboard, forest, goaland, yavapai, goldmine, threetowers, poison, arches, tron, japan, dream, volcano, starry, osiris, moon, desert, mountain

![](/tutorial-images/environment.png)

### Create a custom environment

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload an image for the sky and another one for the ground

- Copy the generated link and paste it into a `sky` and `plane` objects. See the example below:

```html
<a-sky src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/skyWclouds.jpg"></a-sky>

<a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/dry-ground.jpg"rotation="-90 0 0"
width="1000" height="1000" material="repeat: 500 500 ;"></a-plane>
```

## Step 5: Import external 3D models related to your futuristic topic

- Using your Polycam account, explore 3D models from its library: https://poly.cam/explore

- Download a 3D model in the format GLTF format

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload the 3D model you found

- Copy the generated link and paste it into a `a-gltf-model` object. See the example below:

```html
<a-gltf-model src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/Rebbeca%20Street%20Alley.glb" position="11 1 -37.4" scale="0.5 0.5 0.5" rotation="0 80 0"
></a-gltf-model>
```

## Step 6: Use images to support your futuristic artwork

- Add 3D object below the environment you created in step 4. You can select any object from this list: [https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html](https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html)

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload an image of your choice. The website will generate a link to your image.

- Copy the link and paste it in your scene's object. See the example below:

```html
<a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/robot-toy.jpg"
color="white" height="10" width="10" position="0 5 -15"></a-plane>
```
![](/tutorial-images/futuristic-image-on-object.png)

## Step 7: Add videos to support your futuristic artwork

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload a video. The website will generate a link to your video.

- Replace the link from the video element below with the link to your uploaded video

```html
<video id="myVideo" src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/robot_hand.mp4" loop="true" crossorigin="anonymous"></video>
```

- Create an `a-video` object where the video will play:

```html
<a-video src="#myVideo" width= "5" height="5" position="5 2 -5"></a-video>
```

- Add a button and an event listener to play/pause the video and audio when clicking. Add it after the `scene` closing tag `</a-scene>`

```html
<!-- Play button for user interaction -->
  <button id="playButton" style="position: absolute; top: 20px; left: 20px; z-index: 999;">Play Video and Sound</button>
```

 ```javascript

  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const video = document.querySelector('#myVideo');
      const audio = document.querySelector('#myAudio');
      const playButton = document.querySelector('#playButton');

      playButton.addEventListener('click', () => {
        // Play video if not already playing
        if (video.paused) {
          video.play();
        }

        // Play audio if not already playing
        if (audio.paused) {
          audio.play();
        }

        // Hide play button after interaction
        playButton.style.display = 'none';
      });
    });
  </script>
```

![](/tutorial-images/futuristic-video-on-object.png)


## Step 8: Add animation to your objects

- Change the x, y, or z position by adding the following code inside of your objects:

```html
animation="property: object3D.position.x; to: 2.2; dir: alternate; dur: 2000;
loop: true"
```
- Add rotation to your objects:

```html
animation="property:rotation; to: 0 360 0; dur: 2000; loop: true"
```

## Step 9: Submit your artwork to Avenue to Learn

- In your Codecademy workspace generate a share link by clicking the "Share" > "Public: Anyone with a
link can view"

- Submit the link to Avenue to Learn

## Complete example code using a custom environment

- Check the complete working code below:

```html
<html>
<head>
<!-- The next two lines of code are the A-Frame libraries -->
<script src="https://aframe.io/releases/1.6.0/aframe.min.js"></script>
<script src="https://unpkg.com/aframe-environment-component/dist/aframe-environment-component.min.js"></script>


</head>
<body>
<!-- The scene, environment and objects -->
<a-scene id="myScene">
<a-camera><a-cursor></a-cursor></a-camera>

<a-assets>

  <video
  id="myVideo"
  src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/asteroids.mp4"
  loop="true"
  crossorigin="anonymous"
  ></video>

  <audio
        id="myAudio"
        src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/audios/space-sounds.mp3"
        loop="true"
        crossorigin="anonymous"
      ></audio>

</a-assets>

<!-- custom sky  -->
<a-sky src="#myVideo"></a-sky>

<!-- custom ground  -->
 <a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/dry-ground.jpg" rotation="-90 0 0"
width="1000"
height="1000"
material="repeat: 500 500 ;"
></a-plane>

<!-- hamilton alley -->
<a-gltf-model
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/Rebbeca%20Street%20Alley.glb"
position="11 1 -37.4"
scale="0.5 0.5 0.5"
rotation="0 80 0"
></a-gltf-model>


<!-- abandoned building -->
<a-gltf-model
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/abandoned-building.glb"
position="-10 2 -50"  
rotation="-2 0 -2"
></a-gltf-model>

<!-- tim hortons cup -->
<a-gltf-model
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/tim-hortons-cup.glb"
scale="0.5 0.5 0.5"
rotation="0 0 -30"
position="20 -5 -100"
animation="property:rotation; to: 0 0 -90; dur: 60000; loop: true"
></a-gltf-model>

<!-- hamilton arch -->
<a-plane
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/downtown_Hamilton_arch.png"
width="50"
height="17"
position="0 5 -13"
material="transparent: true; alphaTest: 0.5;"
></a-plane>

</a-scene>

<!-- Play button for user interaction -->
  <button id="playButton" style="position: absolute; top: 20px; left: 20px; z-index: 999;">Play Video and Sound</button>

<!-- The code that makes the video play -->

  <script>
    document.addEventListener('DOMContentLoaded', () => {
      const video = document.querySelector('#myVideo');
      const audio = document.querySelector('#myAudio');
      const playButton = document.querySelector('#playButton');

      playButton.addEventListener('click', () => {
        // Play video if not already playing
        if (video.paused) {
          video.play();
        }

        // Play audio if not already playing
        if (audio.paused) {
          audio.play();
        }

        // Hide play button after interaction
        playButton.style.display = 'none';
      });
    });
  </script>
</body>
</html>
```
