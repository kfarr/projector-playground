<img alt="Magic Matta" src="./assets/img/header-magic-matta.png" />

<b>Magic Matta</b> renders "magic carpet" style games and experiences for children and children at heart using physical toy "controllers" tracked with HTC Vive Trackers combined with a top-down projector display.

This requires special hardware to run, explained below in detail. This project attempts to use open-source tools such as WebXR and A-Frame where practical. (Why the name? "matta" is swedish for carpet or rug and Magic Carpet is a reserved trademark.) This is a work in progress and does not work easily without significant manual configuration.

## Pictures
[<img width="30%" src="./docs/MAGIC-MATTA-20190620_173429.jpg" /> <img width="30%" src="./docs/MAGIC-MATTA-gray-area-showcase_06192019_13.jpg" /> <img width="30%" src="./docs/MAGIC-MATTA-gray-area-showcase_06192019_15.jpg" />](https://medium.com/@kfarr/creating-magic-matta-for-the-2019-1-gray-area-showcase-37df8f5d8aa0)

Photo Credits: [Mariah Tiffany](http://www.mariahtiffany.com/)

## Who and Why?
This project was [created during the Gray Area Foundation 2019.1 Incubator by Kieran Farr](https://medium.com/@kfarr/creating-magic-matta-for-the-2019-1-gray-area-showcase-37df8f5d8aa0). )[All other model and software credits found here](/docs/CREDITS.md#credits).) Here is a quick summary of the project motivations:
* Provide a VR experience that kids can see without a headset. Create a fun toy that can also teach things
* Experiment with different input styles -- what can you do with many controllers with no buttons?
* Try to have "multimodal" experience (allow simultaneous headset and projector use with synced scene)
* Uses HTC Vive instead of computer vision for higher accuracy and lower latency of toy tracking making development simpler by ignoring CV complexities

# Project Setup Instructions

## Step 1 - Pre-Requisite Equipment
Let's start with hardware requirements before we get too excited about software setup.
* A PC with HTC Vive calibrated with room space
* A projector mounted about 1.5 meters off the ground pointing downward at the floor. Measure the total size of the projected screen size in meters. (You can get started without this, but the project won't be complete without.)
* Optional - A reflective bright "screen" on the floor that matches the projected screen size. You can use a white carpet patch or white butcher (large format) paper. You can find carpet "remnants" that work well for this at local carpet stores for as low as $10.
* Optional - A separate computer to feed the projector or you can use the same Vive PC for this.

## Hardware Setup
* First choose an area within the HTC Vive lighthouse tracker boundaries for the projector:
<img src="./docs/projector-placement-topdown.png" /><br />
Top-down view: red represents the area of the projected screen. Screen can be anywhere within the lighthouse tracker bounds. It can be any dimensions (portrait or landscape aspect ratio) but make sure it is at a right angle to the lighthouse tracker bounds.
* Mount the projector approx 1.5m off the floor facing down. Most projectors include a 1/4" tripod mount thread (female), you can get clamps with a 1/4" thread (male) to easily mount a mini projector on a table, attach to shelves, etc.
<img src="./docs/projector-placement-side.jpg" /><br />
Side view: suggested mounting heigh of 1.5m, depends on your projector's optics and desired screen size.
* For recommendations on projector and mounting equipment, <a href="https://github.com/chaimgingold/Tabla/#recommended-camera-and-projector">see instructions from La Tabla, another cool projector based XR project</a>

## Software Setup
* On a PC with HTC Vive, clone the repo, `npm install`, `npm start`
* Use your favorite webvr enabled browser like Firefox or Supermedium to navigate to localhost:8080/server.html
* Use the right Vive controller to position the virtual projector to match the real-life position and press the trigger.
* On the same or another computer hooked up to the projector, use any browser (webvr support not required) to open [SERVER IP]:8080/client.html
* Press the "init" button and use the on-screen adjustment buttons to tweak the alignment of the projector and the actual controller positions.
* The bounds of this client projector are now defined.

## Experimental
Using exokit
node . -x webvr http://localhost:8080/server.html

## Future ideas
* orthogonal camera instead of perspective, see notes in codebase
* more instructions for calibration
* next button freeze rectangle, then adjust camera position
* feature multiple minigames, switch by shaking controller
* drawing feature (like babypi), start drawing when controller is pointed up like a pen (small end down)
* Vive tracker support for more inputs
* physics minigames (see simple boilerplate project https://glitch.com/edit/#!/boiling-alligator?path=index.html:27:10)

Credits:
- magic wand - https://commons.wikimedia.org/wiki/File:Magic_Wand_Icon_229981_Color.svg
- magic matta word art - https://makewordart.com/
