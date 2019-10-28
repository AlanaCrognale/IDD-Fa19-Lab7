# Video Doorbell, Lab 7

*A lab report by Alana C. Student*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**

[HelloYou](https://github.com/AlanaCrognale/IDD-Fa19-Lab7/blob/master/HelloYou.MOV)

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**

PictureServer.js adds additional code to incorporate serial communication for the webcam, using the NodeWebCam variable.  From this, pictureServer.js adds the additional functionality to capture and save an image on the server when the corresponding button is pressed.  The initialization variables are also set as 'var' in pictureServer.js, while they are set as 'const' in server.js.

**b. Include a video of your working video doorbell**

[Doorbell](https://github.com/AlanaCrognale/IDD-Fa19-Lab7/blob/master/doorbell.MOV)

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**

My first thought was to add a doorbell ring sound when a picture was taken.  I tried a variety of different npm packages, including 'play-sound-mplayer', 'play-sound', 'audio-play', 'node-stream-player', 'player', and 'soundfont-player'.  At first, I was having a lot of issues with getting any package to work because some of the packages are not up-to-date, so that when attempting to install the packages and/or any dependencies, the terminal would throw fatal errors and not allow me to install.  I had the most luck with 'play-sound', which at first threw errors because I realized I had only uploaded my .mp3 doorbell file onto my local github repository, but not on the pi server's github repository.  Even after this was fixed and no more errors were thrown, I was simply getting no sound.  I tried running terminal commands to simply play the mp3 file separate from any javascript code using the pi's built in omxplayer command, and was getting no errors, but again no sound.  After several hours of debugging, I decided to switch to looking into image manipulation as opposed to sound.  I tried working with the suggested gm package but was unsuccessful in returning no errors when the button was pressed and the image was captured, getting cryptic errors difficult to debug.  I tried a few other image manipulation libraries including adding a watermark or changing the colorscheme of the captured image, but it was difficult to tell any difference due to the camera's heavy exposure.  Finally, I decided to implement a feature which displayed the current time in the console once the button was pressed and the image was captured, so that you can see exactly what time a person tried to 'ring' the doorbell, using the 'get-date' npm package.  I also added a button to display the current time on the page, editing client.js and index.html.

**b. Upload a video of your working modified project**

[Modified](https://github.com/AlanaCrognale/IDD-Fa19-Lab7/blob/master/modified.MOV)
