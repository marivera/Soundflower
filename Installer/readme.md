# Soundflower
*Inter-application Audio Driver*

Soundflower is a virtual audio device that provides an easy and simple way for Max/MSP and other applications to send and receive audio to and from any other application. Running with very low latency and cpu usage, Soundflower allows each client application to use its usual buffer size.

## Installing Soundflower

Run the Soundflower Installer.pkg. You will be asked for an administrator account password. One file, Soundflower.kext, will be installed in the Extensions Folder.

##Using Soundflower

Soundflower presents itself as one of two coreaudio devices. In most cases, you will want to use the 2-channel device.

To send the output of one application to another, simply select Soundflower as the output device within the first application and Soundflower as the input device within the second application.

If an application does not allow you to specify audio devices, you can make Soundflower the default input or output device inside the Sound panel in the System Preferences, or with the Audio MIDI Setup utility application.

The 16-channel device is provided for more complex routing situations, and can be used with more than two applications simultaneously if the applications support audio routing to any channel, as Max/MSP does.

Note that Soundflower's audio channels represent a global audio space. If more than one application is sending its output to the same channel, the audio will be mixed. If you want an application to send and receive audio through Soundflower, (for instance using Max/MSP to manipulate and return another application's audio) you must send and receive the audio on different audio channels or a feedback loop will be created.

*Example*

*To send audio from iTunes to Max/MSP, open the System Preferences and select Soundflower (2ch) as the device for sound output inside the Sound panel. Then, inside Max/MSP's DSP Status Window, select Core Soundflower (2ch) as the input device. All output of iTunes should now be sent to Max/MSP's adc~ object.*

## Troubleshooting

If you are hearing clicks or breakups, try increasing the buffer size of both applications (set within each application).

## Removing Soundflower

From an account with administrator privileges, double-click on the Uninstall Soundflower.scpt file. This will run an AppleScript, in which you will be asked for your password.

## History
The Soundflower Change Log is maintained online at: `http://code.google.com/p/soundflower/wiki/ChangeLog`

A more detailed history can be found at: `http://github.com/tap/Soundflower/commits/master`
