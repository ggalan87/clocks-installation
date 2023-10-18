# Clocks installation
This is an on-going installation that is considered in alpha-version.

The installation deals with the feelings that emerge due to time that passes and time that is running out.

The installation comprises of natural objects (clocks), a sensing device (AI-camera) and a microcontroller (Arduino) to orchestrate interactive visual and auditory experiences.

The installation is built using [ossia score](https://ossia.io/score/about.html), an open-source media sequencer

## The installation
*Spoiler alert!*

The installation comprises of three scenes. The first and second scene play in a loop, while the third scene intervenes upon interaction of a person with the sensing device.

The first scene includes high level representation of time by depicting a video collage of public clocks. The second scene includes a video collage with more personal clocks and objects that depict more explicitly that the time is running out. In the mean time ticks of the natural clocks are constantly heard and digital samples of clock ticks are heard in an increased intensity. 

The third scene has the role of the relief as everything stops and a portion of a poem is heard as soon as person interacts with the sensing device. In the end of the scene or if the person stops interacting the installation starts all over again from the first scene.

### Hardware setup
The hardware setup comprises of a laptop, an Arduino microcontroller, an [AI-camera](https://shop.luxonis.com/collections/home-page/products/oak-d-lite-1) and several clocks. The installation also encompasses few other relevant objects and lights.

### Implementation details
The laptop runs the score project and also serves as host for the Arduino and the AI-camera. The Arduino is ment to operate a relay switch. The switch controlls the power delivery to the clocks, essentially stopping and starting their operation upon request via a serial message. The AI-camera runs a face landmarks detection model and a small script that runs on the laptop identifies the blink of the eyes. The script also serves as a controller using the OSC protocol and implements two commands, ```eyes-closed``` and ```eyes opened```. These commands are registered in Score project and connected to relevant triggers of the third scene. Essentially the third scene intervenes when the eyes of the person get closed and plays while the eyes remain closed. The installation resets when the eyes open or when the third scene finishes.

## Existing setup
The installation was originally set-up for the Makrovoutes festival in 2022.

An overview of the installation is depicted in the following videos.

## TODO:
* Better presentation of the need for interaction
* Initialize and control lighting sources besided sound and clocks
* Standardize the setup such that it can be reproduced more easily
* Enrich narration using objects, sounds, printed documents, photos etc
