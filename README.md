# snap-gstreamer

  GStreamer is a library for constructing graphs of media-handling components. The applications it supports range from simple Ogg/Vorbis playback, audio/video streaming to complex audio (mixing) and video (non-linear editing) processing.(https://gstreamer.freedesktop.org/)

## Commands
You can use gst-launch-1.0 using the gst-launch app in the snap. 
To check installed plugins, you can use `gst-inspect-1.0`
```
gstreamer.gst-launch
```

## To install
To install the snap from the store, use the snap install command. 
```
snap install gstreamer --devmode
```
## Run image streaming
First, to test gstreamer is working, 
```
gstreamer.videotestsrc-ball
```
or
```
gstreamer.gst-launch videotestsrc pattern=ball ! video/x-raw,width=640,height=480 ! videoconvert ! x264enc ! rtph264pay ! udpsink host=127.0.0.1 port=5600 -v
```

## To build
The snap can be built usng `snapcraft`.
```
sudo snapcraft
```
If the snap is successfully snapped, it can be installed by the following command
```
sudo snap install gstreamer*.snap --dangerous --devmode
```

