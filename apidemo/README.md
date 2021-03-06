Glass Development Kit API Demo
=======


## Live Card Demo

This Glassware demonstrates a simple implementation of the 
[LiveCard](https://developers.google.com/glass/develop/gdk/ui/live-cards) API.

It creates a LiveCard when the app's main activity is first activated (through voice input).
The lifecycle of the LiveCard is associated with that of a background Service (`LiveCardDemoLocalService`).

It also shows how to add a menu to a LiveCard, 
which is bound to the main activity.


## Live Card Demo 2

The purpose of this example is to test 
the ["low frequency rendering" of Live Cards](https://developers.google.com/glass/develop/gdk/ui/live-cards).

It uses an Android `TimerTask` to update the live card's content every 15 seconds.

It also has slightly different behavior from the preivious version "LiveCard Demo"
in that it sets the "NonSlient" flag to true.
If you want to stop the app, tap the LiveCard screen to go back to the main Activity screen,
from which tapping one more will exit the program (after removing the live card, etc.)


## Live Card Demo 3

This demo app includes
sample code for the ["high frequency Live Cards"](https://developers.google.com/glass/develop/gdk/ui/live-cards).
It uses an Ancroid local service which
implements the [LiveCardCallback](https://developers.google.com/glass/develop/gdk/reference/com/google/android/glass/timeline/LiveCardCallback) interface 
to draw on the card's canvas.

The sample app merely draws the solid bacground with a random/time-changing color.



## Touch Gesture Demo

This simple Glass app is based on the sample code
found in the GDK doc: [Touch Gesture](https://developers.google.com/glass/develop/gdk/input/touch).

It adds some minor changes
so that the gesture event is displayed on the screen
(either on a separrate activity or as a Toast,
based on the value of the Config variable, `USE_GESTURE_INFO_ACTIVITY`).

You can start the app through the following voice input.

_OK, Glass._ _Start Gesture Demo_


## Voice Input Demo

This demo app includes two activities: 

* `VoiceDemoActivity` - This is the main activity, and it demonstrates the voice trigger and voice prompt.
* `VoiceDictationActivity` - This activity shows how to call the system-provided Speech Recognition API via the intent type `RecognizerIntent.ACTION_RECOGNIZE_SPEECH`.  

After starting the app via the voice command, _OK, Glass._ _Start Voice Demo_, 
speak _dictate_ at the voice prompt, "next action",
to start the `VoiceDictationActivity`. It can also be activated using the TAP gesture.

Tap to start dictation.


## Camera Demo

This first demo app using Google Glass Camera
relies on the stock Camera activity to take photos.

The path of the photo/image file (JPG) is passed to the calling activity, `CameraDemoActivity`, through the extra param, `Camera.EXTRA_PICTURE_FILE_PATH`. 
The image file at the given path is then polled to check if the file is ready.
If so, it is converted to a bitmatp and it is displyed in the `ImageView` of the livecard.

    Bitmap bitmap1 = BitmapFactory.decodeFile(filePath);
    remoteViews.setImageViewBitmap(R.id.livecard_image, bitmap1);




## Location API Demo

This demo Glassware uses the Android `LocationManager` API
to display the user's location on the LiveCard.
The location is dynamically updated based on the data supplied by a number of location providers
(including the "remote" location provider, if available).

A simple (toy) algorithm is used to get the "best" location information at any given time.



## Sensor API Demo

A number of sample Glassware illustrating
the use of [Android Sensor API](http://developer.android.com/guide/topics/sensors/sensors_overview.html)
are included in the [Sensor Demo directory](https://github.com/harrywye/gdkdemo/tree/master/apidemo/sensordemo).

