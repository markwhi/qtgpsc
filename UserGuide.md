# Introduction #

Once qtGpsc has been [installed](Installation.md) on your machine, and assuming you have access to a [gpsd](http://gpsd.berlios.de/) instance, you can use qtGpsc to connect to the gpsd server and visualise the data coming out of the receiver.

# Starting qtGpsc #

If you have installed from source in the standard location, or if you have obtained qtGpsc via a package repository, there should be an entry in your desktop's applications menu from where you may launch qtGpsc.

Alternatively, it may be started from a terminal as `qtgpsc`. It accepts an optional command-line argument of the form `[gpsd://]server[:port][/device]`, e.g:
```
qtgpsc gpsd://localhost/dev/ttyUSB0
```

# Using qtGpsc #

Upon launching `qtgpsc` its user interface is presented. The host and port details of the gpsd server can be entered in the respective entry fields on the upper part of the window, then pressing connect initiates a connection to the gpsd server.

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot01.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot01.png)

In the event of a failure, an error message will be displayed in the status bar:

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot02.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot02.png)

If on the other hand, a successful connection is established, you will see the data being reported by gpsd. The main window is divided vertically in two halves: on the left hand side textual information is displayed, while the right hand side shows graphical information (currently a skyplot)—̣it is possible to change the relative sizes of the two sides by using the splitter between them. Dragging the splitter all the way to one side will hide one pane or the other.

Three forms of textual data and one graphic are displayed, as described below.

## Position, Velocity, and Time ##

The **Position** pane shows basic information about the receiver's computed position and speed, along with error estimates.  For an explanation of the abbreviations used in the error estimates, set the focus on the field of interest (e.g., by clicking or using the keyboard) and press Shift+F1 for a brief help popup.

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot03.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot03.png)

Using the _Units_ menu it is possible to change the units of measurement from a choice of common units.  These changes take effect immediately and are persistent across sessions.

## Satellite Information ##

The **Satellites** pane shows details of all visible satellites in tabular form: azimuth, elevation, signal to noise ration, and whether the satellite is being used in the solution computation, are all shown.

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot04.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot04.png)

## Raw Data ##

The **Raw Data** text pane lets the user see the raw data stream from the gpsd server in one of three formats: JSON (gpsd's native wire format), NMEA, or the raw receiver data as hexadecimal bytes. The user may copy the data to clipboard or save it to a file by using the buttons provided.

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot05.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot05.png)

## Skyplot ##

The skyplot shows the position of all visible satellites in the sky, in the form of a radial plot where distance from centre represents the satellite's elevation, from 0° to 90°, and its direction from the centre represents the azimuth from the receiver, with True North being up.

![http://wiki.qtgpsc.googlecode.com/hg/ScreenShot06.png](http://wiki.qtgpsc.googlecode.com/hg/ScreenShot06.png)

The skyplot can be copied to the clipboard by right-clicking on it to activate the context menu and selecting the relevant option from it.

# Miscellaneous Features #

From the _Edit_ menu, it is possible to copy the current position data to the clipboard as either comma separated values, or KML.

The skyplot graphic can be copied as described above and pasted into a file, e.g., using GIMP, or directly into a word processing document or similar.

It is possible to configure qtGpsc as a handler for the `gpsd://` scheme by associating it to the `uri/gpsd` URI (e.g., via _System Settings_ in KDE).