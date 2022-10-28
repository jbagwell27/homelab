# Trackball Config for ELECOM Huge

Adjust acceleration and scroll button for the ELECOM Huge Trackball mouse.

Gnome settings override the scroll button by default. set it by running:
```
gsettings set org.gnome.desktop.peripherals.trackball scroll-wheel-emulation-button 12 #button that you want to set to scroll
```

Create a file: `/etc/X11/xorg.conf.d/99-elecom-huge.conf` (this can also be added to the same file as above)
```ini
Section "InputClass"
    Identifier   "Elecom HUGE scroll config"
    MatchDriver  "libinput"
    MatchVendor  "ELECOM"
    MatchProduct "HUGE TrackBall"
    #Option 	 "AccelProfile" "linear"
    Option 		 "AccelProfile" "adaptive"
    Option 	 	 "AccelSpeed" "1"
    Option       "ScrollMethod" "button"
    Option       "ScrollButton" "12"
    Option       "ButtonMapping" "1 2 3 4 5 6 7 8 9 9 1 12"
EndSection

```


## CLI command

```bash
xinput set-prop "pointer:ELECOM TrackBall Mouse HUGE TrackBall" 'libinput Button Scrolling Button' 12
xinput set-prop "pointer:ELECOM TrackBall Mouse HUGE TrackBall" 'libinput Scroll Method Enabled' 0 0 1
```
