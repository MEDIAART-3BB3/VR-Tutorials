# Tutorial for Virtual Reality Artwork: "World-Building and Futurism"

## TABLE OF CONTENTS
- [Step 1: Create a workspace in Codecademy](#step-1-create-a-workspace-in-codecademy)
- [Step 2: Add the template code to your workspace](#step-2-add-the-template-code-to-your-workspace)
- [Step 3: Initialize the scene](#step-3-initialize-the-scene)
- [Step 4: Design a futuristic environment (preset or custom)](#step-4-design-a-futuristic-environment-preset-or-custom)
- [Step 5: Add futuristic 3D models to your scene](#step-5-add-futuristic-3D-models-to-your-scene)
- [Step 6: Add a button to play and pause audios and videos](#step-6-add-a-button-to-play-and-pause-audios-and-videos)
- [Step 7: Add a futuristic audio](#step-7-add-a-futuristic-audio)
- [Step 8: Add videos to enhance your futuristic artwork](#step-8-add-videos-to-enhance-your-futuristic-artwork)
- [Step 9: Use images to support your futuristic artwork](#step-9-use-images-to-support-your-futuristic-artwork)
- [Step 10: Animate objects in your scene](#step-10-animate-objects-in-your-scene)
- [Step 11: Submit your completed artwork](#step-11-submit-your-completed-artwork)
- [Example of completed artwork code (using a custom environment)](#example-of-completed-artwork-code-using-a-custom-environment)

## Step 1: Create a workspace in Codecademy

- **Login** to Codecademy, then **go to** Workspaces > Add workspace > HTML/CSS/JS. **Title** your workspace.

## Step 2: Add the template code to your workspace

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

## Step 3: Initialize the scene

- **Paste** the following code between the `<body></body>` tags

```html
<a-scene id="myScene">

</a-scene>
```

## Step 4: Design a futuristic environment (preset or custom)
### Option 1: Create a preset environment

- **Paste** the following code between the `<scene></scene>` tags

```html
<a-entity environment="preset: tron; dressingAmount:500"></a-entity>
```

- **Change** the preset environment by choosing from the following list:
default, contact, egypt, checkerboard, forest, goaland, yavapai, goldmine, threetowers, poison, arches, tron, japan, dream, volcano, starry, osiris, moon, desert, mountain

![](/tutorial-images/environment.png)

### Option 2: Create a custom environment

- **Go to** [pexels.com](https://www.pexels.com/) to **explore** `sky` and `ground` images. **You don't need to log in to download images**. Pexels is just one alternative. You can download images from other places you like

- **Select and download** a `sky` and `ground` image

- **Go to** [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload the images

- **Copy** the generated links and paste them into a `sky` and `plane` tags. See the example below:

```html
<a-sky src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/skyWclouds.jpg"></a-sky>

<a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/dry-ground.jpg"rotation="-90 0 0"
width="1000" height="1000" material="repeat: 500 500 ;"></a-plane>
```
![](/tutorial-images/custom-environment.png)

## Step 5: Add futuristic 3D models to your scene

- **Log in** to your Polycam account to explore free 3D models: [https://poly.cam/explore](https://poly.cam/explore)

- **Select and download** a 3D model in GLTF format

- **Go to** [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload the 3D model

- **Copy** the generated link and paste it into a `a-gltf-model` tag. See the example below:

```html
<a-gltf-model src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/abandoned-building.glb"
position="-10 2 -50" rotation="-2 0 -2" ></a-gltf-model>
```
![](/tutorial-images/external-model.png)

## Step 6: Add a button to play and pause audios and videos

- **Add** a button and an event listener to play/pause the video and audio when clicking. Copy the following after the closing tag `</a-scene>`:

```html
<!-- Play button for user interaction -->
  <button id="playButton" style="position: absolute; top: 20px; left: 20px; z-index: 999;">
    Play Video and Sound</button>
```

 ```javascript

 <script>
  // The code that makes the video and sound play
   document.addEventListener('DOMContentLoaded', () => {
     const mediaElements = document.querySelectorAll('video, audio');
     const playButton = document.querySelector('#playButton');

     playButton.addEventListener('click', () => {
       mediaElements.forEach(media => {
         if (media.paused) {
           media.play();
           playButton.textContent = 'Pause Video and Sound';
         } else {
           media.pause();
           playButton.textContent = 'Play Video and Sound';
         }
       });
     });
   });
 </script>
```

## Step 7: Add a futuristic audio

- **Log in** to [freesound.org](https://freesound.org/) using the class' username `mediaart3bb3` and the password `mcmaster123` to **explore** futuristic audios

- **Select and download** a futuristic audio

- **Go to** [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload the audio

- **Copy** the generated link and paste it into an `audio` element. See example below:

```html
<audio src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/audios/space-sounds.mp3" loop="true"      crossorigin="anonymous" ></audio>
```

- **Play** the audio by clicking the "Play Video and Sound button" from step 6


## Step 8: Add videos to enhance your futuristic artwork

- **Go to** [pexels.com](https://www.pexels.com/). to **explore** futuristic videos. **You don't need to log in to download videos** Pexels is just one alternative. You can download videos from other places you like

- **Select and download** a futuristic video

- **Go to** [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload a video

- **Copy** the generated link and paste it into a `video` element. See example below:

```html
<video id="myAsteroidsVideo" src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/asteroids.mp4"
  loop="true" crossorigin="anonymous"></video>
```

- **Create** an `a-video` object where the video will display:

```html
<a-video src="#myAsteroidsVideo" width= "5" height="5" position="5 2 -5"></a-video>
```
- **Play** the video by clicking the "Play Video and Sound button" from step 6

## Step 9: Use images to support your futuristic artwork

- **Go to** [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload an image related to your futuristic topic

- **Copy** the generated link and paste it into an object, like a plane. See the example below:

```html
<a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/downtown_Hamilton_arch.png" width="50"
height="17" position="0 7 -13" material="transparent: true; alphaTest: 0.5;" ></a-plane>
```
![](/tutorial-images/futuristic-image.png)


## Step 10: Animate objects in your scene

- **Change** the x, y, or z position by adding the following code inside of your objects:

```html
animation="property: object3D.position.x; to: 2.2; dir: alternate; dur: 2000;
loop: true"
```
- Add rotation to your objects:

```html
animation="property:rotation; to: 0 360 0; dur: 2000; loop: true"
```

## Step 11: Submit your completed artwork

- **Click** "Share" > "Public: Anyone with a link can view" in your Codecademy workspace

- **Copy and Submit** the link to Avenue to Learn

## Example of completed artwork code (using a custom environment)

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

<a-assets>
  <!-- An audio of space sounds -->
  <audio
  src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/audios/space-sounds.mp3"
  loop="true"
  crossorigin="anonymous"
  ></audio>

<!-- A video of space asteroids -->
  <video
  id="myAsteroidsVideo"
  src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/asteroids.mp4"
  loop="true"
  crossorigin="anonymous"
  ></video>

</a-assets>

<!--  a custom sky playing the asteroids video from above -->
<a-sky src="#myAsteroidsVideo"></a-sky>

<!-- a custom ground  -->
 <a-plane src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/dry-ground.jpg" rotation="-90 0 0"
width="1000"
height="1000"
material="repeat: 500 500 ;"
></a-plane>

<!-- external 3D model of an abandoned building found in Polycam's website -->
<a-gltf-model
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/abandoned-building.glb"
position="-10 2 -50"  
rotation="-2 0 -2"
></a-gltf-model>

<!--  external 3D model of a giant Tim Hortons cup that I made in Tinkercad -->
<a-gltf-model
src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/3d-models/tim-hortons-cup.glb"
scale="0.5 0.5 0.5"
rotation="0 0 -30"
position="20 -5 -100"
animation="property:rotation; to: 0 0 -90; dur: 60000; loop: true"
></a-gltf-model>

<!-- An image of the Hamilton arches -->
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
    const mediaElements = document.querySelectorAll('video, audio');
    const playButton = document.querySelector('#playButton');

    playButton.addEventListener('click', () => {
      mediaElements.forEach(media => {
        if (media.paused) {
          media.play();
          playButton.textContent = 'Pause Video and Sound';
        } else {
          media.pause();
          playButton.textContent = 'Play Video and Sound';
        }
      });
    });
  });
</script>

</body>
</html>
```
