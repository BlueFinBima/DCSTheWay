## This fork has been archived, and the parent appears to be more active.  I would suggest checking with the parent repo.


# DCSTheWay
Imports waypoints from DCS F10 map into the plane navigation system, like a Data Transfer Cartridge.
Special thanks to kukiric for helping out with the lua side of things!

## What does it do?
You choose points on the F10 map, press a button, and those points will be entered as steerpoints into your plane.  

## What is supported?
Supported modules:
* F-16 
* F/A-18 (make sure you are not in the TAC menu)
* A-10C and A-10C2
* Mirage 2000
* AV8BNA Harrier
* Ka-50 Blackshark
* AH-64D Apache 
 
Multiplayer is supported as long as the server has ownship/player exports turned on.

## How to install?
1. Download the latest zip file from the Releases section, and extract `The Way` folder inside it in a convenient location, from where you will run the program. 
2. Copy the `TheWay.lua` file from the folder you just extracted into `Users/YourUsernameHere/Saved Games/DCS/Scripts`. The `DCS` folder name may be `DCS.openbeta` if you are on the openbeta version of the game.
3. Edit the `Export.lua` file there and append this line at the end of the file, and save it:
  ```lua
  local TheWayLfs=require('lfs'); dofile(TheWayLfs.writedir()..'Scripts/TheWay.lua')
  ```
   If there is no `Export.lua` file already existing there, create it yourself, and it should include only the line above.

4. Launch `TheWay.exe` and go fly!

If you are updating from an older version, simply download the newest release, extract your new `The Way` folder ontop of your old one, replacing your existing files with the new ones. Also don't forget to copy your new `TheWay.lua` file into Saved Games, and override your old one there.

## How to use? 
Video tutorial here:

[![DCSTheWayVideoThumbnail](http://img.youtube.com/vi/0PHWXWClENQ/0.jpg)](http://www.youtube.com/watch?v=0PHWXWClENQ)

Or follow these steps:
1. Launch `TheWay.exe`.
2. Click `Start selecting on map`, and a selection dot will show on screen.
3. Enter the F10 map, position the dot on top of the desired place you wish to mark, and click `Select point`.
Repeat this step to mark as many points as you want.
4. When finished, enter the F1 cockpit view and click `Begin transfer to DCS` to begin the transfering process.
It is advised that you refrain from additional cockpit inputs until the waypoints have been loaded.

### Notes
1. For those with non-standard monitor configurations, especially those where the UI is displayed on a different monitor to DCS (and/or different size to DCS), then the following command line options for `TheWay.exe` should allow the crosshair to appear in the correct location.
2. Specifying an `outputfilename` will save waypoints collected by TheWay to the external file specified when the `Begin transfer to DCS` button is pressed.
3. `suppressdcsoutput` will not send data to DCS when the `Begin transfer to DCS` button is pressed.  (only makes sense in conjunction with `outputfilename`)
4. Specifying an `inputfilename` will process waypoints stored in the external file specified. 
5. Unfortunately stdout does not currently display output due to the way that `TheWay.exe` is built so the help is shown below.
```
usage: Help
 -?,--help                                 Show Help
 -c,--cornerposition <TL | TR | BL | BR>   Corner position where the "The
                                           Way" window is placed.
                                           <TopLeft | TopRight |
                                           BottomLeft | BottomRight>
 -d,--displaynumber <displaynumber>        Number of the display device
                                           used for the F10 screen
 -h,--height <height>                      Height of the UI display area
                                           used for the F10 map
 -i,--inputfilename <filename>             filename of the file containing
                                           saved waypoints.
 -o,--outputfilename <filename>            filename of the file which will
                                           contain the collected
                                           waypoints.
 -s,--suppressdcsoutput                    Used to stop waypoints being
                                           sent to DCS.
 -w,--width <width>                        Width of the UI display area
                                           used for the F10 map
 -x,--left <left>                          Left position of the start of
                                           the UI display area used for
                                           the F10 map
 -y,--top <top>                            Top position of the start of
                                           the UI display area used for
                                           the F10 map
```
The `displaynumber` parameter will not necessary be the same number that appears in the Windows `Display Settings` panel so a little experimentation might be necessary

This is the way.
