# Create a futurist virtual reality scene

###Instructions:

1. Imagine your role in the future
2. Create a virtual reality scene following the steps below
3. Customize your scene by changing the images, videos and 3D objects

##Step 1: Create a workspace in Codecademy

1. Log in to you Codecademy account
2. Click Workspaces > Add workspace > HTML/CSS/JS
3. Add a title to your workspace

##Step 2: Copy the template code below to your workspace's index file

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

##Step 3: Add an empty scene

1. Paste the following code between the <body></body> tags

```html
<a-scene>

<\a-scene>
```

##Step 4: Add a preset environment

1. Paste the following code between the <scene></scene> tags

```html
<a-entity environment="preset: tron; dressingAmount:500"></a-entity>
```

2. Change the preset environment by choosing from the list below:
default, contact, egypt, checkerboard, forest, goaland, yavapai, goldmine, threetowers, poison, arches, tron, japan, dream, volcano, starry, osiris, moon, desert, mountain

#Step 5: Add a 3D object with a futurist image that represents you

1. Add 3D object below the environment you created in step 4. You can select any object from this list: [https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html](https://aframe.io/docs/1.6.0/introduction/html-and-primitives.html)

2. Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload an image of your choice. The website will generate a link to your image.

3. Copy the link and paste it in your scene's object. See the example below:

```HTML
<a-box src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/images/robot-toy.jpg"
color="white" depth="2" height="2" width="2" position="0 0 -5"></a-box>
```

##Step 6: Add a video to an object

1. Create another object. See example below:

```HTML
<a-box id="myBox" src= "#myVideo" width= "2" height="2" depth="2" position="3 2 -5"></a-box>
```

2. Create a video element by copying the code below:

```HTML
<video id="myVideo" src="https://mediaart-3bb3.github.io/vr_assets_fall_2024/videos/robot_hand.mp4" loop="true"
crossorigin="anonymous"></video>
```

3. Go to [https://mediaart-3bb3.github.io/vr_assets_fall_2024/](https://mediaart-3bb3.github.io/vr_assets_fall_2024/) and follow the instructions to upload a video of your choice. The website will generate a link to your video.

4. Replace the link from the video element above with the link to your uploaded video

5. Copy the code below to add a cursor to play/pause your video

```HTML
<a-camera>
<a-cursor></a-cursor>
</a-camera>
```

6. Add an event listener to the object to play/pause the video on click. Add it after the scene closing tag (i.e., </a-scene>).

```HTML
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
