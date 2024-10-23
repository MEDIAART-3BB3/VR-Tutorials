# Create a futurist virtual reality scene - Take-home activity

### Instructions:

1. Imagine your role in the future
2. Create a virtual reality scene following the steps below
3. Customize your scene by changing the images, videos and 3D objects
4. If you submit this assignment you will get a 1% participation point a the end of the semester

## Step 1: Create a workspace in Codecademy

- Log in to you Codecademy account
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

## Step 3: Add an empty scene

- Paste the following code between the <body></body> tags

```html
<a-scene>

</a-scene>
```

## Step 4: Add a preset environment

- Paste the following code between the <scene></scene> tags.

```html
<a-entity environment="preset: tron; dressingAmount:500"></a-entity>
```

- Change the preset environment by choosing from the following list:
default, contact, egypt, checkerboard, forest, goaland, yavapai, goldmine, threetowers, poison, arches, tron, japan, dream, volcano, starry, osiris, moon, desert, mountain

![/tutorial-images/environment.png]

## Step 5: Add a 3D object with a futurist image that represents you

- Add 3D object below the environment you created in step 4. You can select any object from this list: [https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html](https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html)

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload an image of your choice. The website will generate a link to your image.

- Copy the link and paste it in your scene's object. See the example below:

```html
<a-box src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/robot-toy.jpg"
color="white" depth="2" height="2" width="2" position="0 0 -5"></a-box>
```
![/tutorial-images/futuristic image on object.png]

## Step 6: Add another object with a video with a futurist topic

- Create another object. See example below:

```html
<a-box id="myBox" src= "#myVideo" width= "2" height="2" depth="2" position="3 2 -5"></a-box>
```

- Create a video element by copying the code below:

```html
<video id="myVideo" src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/robot_hand.mp4" loop="true"
crossorigin="anonymous"></video>
```

- Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload a video of your choice. The website will generate a link to your video.

- Replace the link from the video element above with the link to your uploaded video

- Copy the code below to add a cursor to play/pause your video

```html
<a-camera>
<a-cursor></a-cursor>
</a-camera>
```

- Add an event listener to the object to play/pause the video on click. Add it after the scene closing tag (i.e., </a-scene>).

```javascript
<script>
// Get the shape and video elements
const box = document.querySelector('#myBox');
const video = document.querySelector('#myVideo');
// Add an event listener to the sphere to play/pause the video on click
box.addEventListener('click', () => {
if (video.paused) {
video.play();
} else {
video.pause();
}
});
</script>
```
- Test your video plays and pauses by placing the cursor (black ring) on your video and making click

![/tutorial-images/futuristic video on object.png]


## Step 7: Add animation to your objects

- Change the x, y, or z position by adding the following code inside of your objects:

```html
animation="property: object3D.position.x; to: 2.2; dir: alternate; dur: 2000;
loop: true"
```
- Add rotation to your objects:

```html
animation="property:rotation; to: 0 360 0; dur: 2000; loop: true"
```

## Step 8: Submit your working scene to get a 1% participation point at the end of the semester

- In your Codecademy workspace generate a share link by cliking the "share" option > "Public: Anyone with a
link can view"
- Paste the link in the following shared file:
[https://mcmasteru365-my.sharepoint.com/:x:/g/personal/navarrol_mcmaster_ca/Ebd5qDcg78lJhA1aWQoQ7gwBxT8H_XFTju54UcJPCsIfTg?e=xl6Qyh](https://mcmasteru365-my.sharepoint.com/:x:/g/personal/navarrol_mcmaster_ca/Ebd5qDcg78lJhA1aWQoQ7gwBxT8H_XFTju54UcJPCsIfTg?e=xl6Qyh)

## Activity solution

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
<a-scene>
<a-entity environment="preset: tron; dressingAmount: 500"></a-entity>

<a-box src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/robot-toy.jpg"
color="white" depth="2" height="2" width="2" position="0 0 -5" animation="property: object3D.position.x; to: 2.2; dir: alternate; dur: 2000;
loop: true"></a-box>

<a-box id="myBox" src= "#myVideo" width= "2" height="2" depth="2" position="3 2 -5" animation="property:rotation; to: 0 360 0; dur: 2000; loop: true"
></a-box>

<video id="myVideo" src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/robot_hand.mp4" loop="true"
crossorigin="anonymous"></video>

<!-- the cursor -->
<a-camera>
<a-cursor></a-cursor>
</a-camera>
</a-scene>

<script>
// Get the shape and video elements
const box = document.querySelector('#myBox');
const video = document.querySelector('#myVideo');
// Add an event listener to the sphere to play/pause the video on click
box.addEventListener('click', () => {
if (video.paused) {
video.play();
} else {
video.pause();
}
});
</script>

</body>
</html>
```
