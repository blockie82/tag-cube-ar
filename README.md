# Tag Cube AR

Hold a paper cube up to your webcam and a 3D model appears on top of it, following the cube as you move and turn it.

The cube has an AprilTag (tag36h11, IDs 0–5) printed on each face. The app finds the tags in the camera picture, works out where the cube is, and draws your own `.glb` model on it. It also creates a printable PDF of the cube, ready to cut out and fold, on A4 or US Letter paper.

Everything runs in your browser. The camera picture and your models are never uploaded anywhere.


## Screenshots
**1. Tracking the cube.** The app has found two faces (tags 2 and 3, outlined in yellow) and a caffeine molecule model stands on top of the cube.

<img width="2560" height="944" alt="ffd70ee1-a3ff-43b1-8d59-816980fffde1" src="https://github.com/user-attachments/assets/73fb8723-34e1-4f6c-8929-112eb1f3a9df" />




 
**2. The printable cube.** Cut the solid lines, fold the dashed ones and glue the tabs.

<img width="2000" height="1414" alt="156d4845-5e53-41c9-ace4-743998fc508b" src="https://github.com/user-attachments/assets/c623d86a-20c9-4401-ac9f-20e4b5e7d04e" />



## Quick start

1. Download the app. Either:
   - Select the green **Code** button, then **Download ZIP**, and unzip it; or
   - Open `tag-cube-ar.html` in this repository, select the **Download raw file** button (the download icon above the file), and save it.
2. Double-click `tag-cube-ar.html` to open it in Chrome, Edge, Firefox or Safari.
3. Select **Start camera** and allow camera access when your browser asks.

No install, server or Git knowledge is needed. You do need an internet connection the first time, so the browser can load the 3D, tag-detection and PDF libraries.

## Making the cube

1. In the bar under the preview, choose **A4** or **US Letter**, set the cube edge (60 mm by default) and select **Download cube PDF**.
2. Print it at 100% / "Actual size", not "Fit to page". Check the 50 mm ruler at the top of the page with a real ruler.
3. Thin card (160–220 gsm) works best. Matte paper is better than glossy, because glare on a tag stops it being read.
4. Cut along the solid lines. Score and fold the dashed lines away from you, so the printing ends up on the outside.
5. Glue the tabs inside the cube.

Each face carries one tag: 0 front, 1 right, 2 back, 3 left, 4 top, 5 bottom. The model stands on the top face (tag 4), so keep that face up.

## Using the app

1. **Camera.** Select **Start camera**. If you have more than one camera, pick it from the list. *Mirror* flips the view like a selfie camera.
2. **Show the cube.** The numbered chips under the preview light up for each tag the app can see. Two or three visible faces give the steadiest result.
3. **Load your model.** Select **Upload .glb**, or drag a `.glb` file onto the preview. *Sample* brings back the built-in model. Animated models play automatically.
4. **Place the model.**
   - *On top* stands the model on the cube. *Inside cube* centres it in the cube.
   - *Size* is measured in cube edges, so 1.0 is as wide as the cube.
   - *Turn* rotates the model on the cube.
   - *Cube hides what is behind it* stops the model showing through the cube when it is partly behind it.
5. **Fine-tune the tracking.**
   - *Camera field of view*: if the model slides as you tilt the cube, adjust this until it stays put. Most laptop webcams are 55–70°.
   - *Smoothing*: higher values make the model steadier, lower values make it react faster. Try 0.75–0.85 if it shakes when the cube is still.
   - *Detect at*: 960 px helps with small or distant cubes but is slower.
   - *Outline tags* and *Cube wireframe* show what the app is detecting.

## Tips

- Light the cube evenly and avoid strong reflections on the tags.
- Keep your fingers off the black squares and their white borders. Hold the cube by its edges or corners.
- Keep the cube flat and the creases sharp. Bent or bulging faces make the model wobble.
- A cube edge of 50–60 mm works well at arm's length from a laptop webcam. For a cube further away, print it as large as the paper allows.
- Models made for the web (a few MB or less) load fastest. Draco- and Meshopt-compressed `.glb` files are supported.
- The cube is measured in proportions, not millimetres, so tracking still works if the printer scales the page slightly.

## Known limitations

- Only one cube can be tracked at a time, and it must use tag IDs 0–5 from the tag36h11 family.
- The camera's field of view is a setting rather than being measured, so you may need to adjust it once for your camera.
- If only one face is visible and it is seen almost straight on, the model can briefly flip or wobble. Tilt the cube so two faces show.
- Fast movement can blur the tags so they are not detected for a moment. The model reappears as soon as the cube is still enough to read.
- Camera access only works when the file is opened directly from your computer or from an `https://` address. It does not work inside some preview windows or embedded viewers.
- `.gltf` files that reference separate texture or `.bin` files will not load. Use a single `.glb` file.

## Created with Claude

This tool was designed and written by [Claude](https://claude.ai), an AI assistant made by [Anthropic](https://www.anthropic.com), through a conversation with the repository owner. The owner directed the project and tested the result.

It uses these open-source libraries, loaded from public CDNs:

- [three.js](https://threejs.org) for the 3D view (MIT License)
- [js-aruco2](https://github.com/damianofalcioni/js-aruco2) for tag detection (MIT License), including the tag36h11 codes from the [AprilTag](https://april.eecs.umich.edu/software/apriltag) project at the University of Michigan (BSD License)
- [jsPDF](https://github.com/parallax/jsPDF) for the printable cube (MIT License)

## Status

This project is shared as-is. It is not actively maintained and contributions (issues, pull requests) are not being accepted. You are free to copy the single `tag-cube-ar.html` file and adapt it for your own use. It has no build step.


## License

Released under the [MIT License](LICENSE). You're free to use, copy, modify and share this tool, but it comes with no warranty.
