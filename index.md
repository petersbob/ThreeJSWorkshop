## What is Three.JS?

A javascript API for rendering 3D graphics (and 2D if you want).

It uses hardware ecceleration and is supported on all modern web browers.

## Do I Need a Plugin?

No you do not!! Thanks to widespread support for WebGL.

## What Can Three.JS Do?

All sorts of stuff.

Beyond the expected games and websites, Three.JS has been used for advertisments and music videos.

### Lets Get Started!!

We are going to start with the Hello World of Three.JS programming, a rotating cube.

1. Start by creating project directory and give it a name. I'm gonna use ThreeJS_HW. Inside of this directory create one file named index.html and another directory named js. Naviagate to [this github page](https://github.com/mrdoob/three.js/tree/dev/build) and download a Three.JS build.

Set up a basic html page to use the downloaded three.js file. Also create an empty javscript tag fro our work.

It should look like this

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset=utf-8>
		<title>Three.JS Workshop</title>
		<style>
			body { margin: 0; }
			canvas { width: 100%; height: 100% }
		</style>
	</head>
	<body>
		<script src="js/three.js"></script>
		<script>
			// This is where the rest of the work will go
		</script>
	</body>
</html>
```

2. Next we must create three important things, the scene, the camera, the renderer.

   -The scene is thing we are adding everything else to.
   -The camera is how we view the scene.
   -The renderer creates the image for our camera to see.

```javascript
	var scene = new THREE.Scene();
	var camera = new THREE.PerspectiveCamera( 75, window.innerWidth / window.innerHeight, 0.1, 1000 );

	var renderer = new THREE.WebGLRenderer();
	renderer.setSize( window.innerWidth, window.innerHeight );
	document.body.appendChild( renderer.domElement );
```

The type of camera we are using is a perspective camer that will reflect how we naturally see the world. It takes four parameters.

1. Field of View (in degrees)
2. Aspect Ratio (set to the ration of window width to height)
3. Near (distance to stop rendering close up objects)
4. Far (distance to stop rendering far away objects)

We also created a renderer that will render how scene with WebGL. It takes two parameters.

1. Render width (set to the width of the window)
2. Render height (set to the height of the winow)

Then we add the render element (a <canvas> element) to our html document.