# nvidia-forcecomp
Tray application for toggling changing state of 'ForceFullCompositionPipeline' on nVidia graphics cards.

## Why?
By default, nVidia cards using the blob driver experience tearing. Most notably when scrolling 
applications such as firefox. If ForceFullCompositionPipeline is enabled, the tearing 
dissipates. However, frame rates in OpenGL applications (such as full screen games) tend to 
consume more GPU time. This tray icon allows you to toggle the state on the fly, so if you want 
to browse the web, left click the icon for a tear-free environment. Feel like playing a game? 
Right click the icon before launching it. The reason framerates drop in fulslcreen applications, 
is because ForceFullCompositionPipeline literally forces the screen to be redrawn even when 
nothing has changed, and generally takes up more GPU time.

An example of ForceFullCompositionPipeline being used in /etc/X11/xorg.conf:

```
Section "Screen"
    Identifier     "Screen0"
    Device         "Device0"
    Monitor        "Monitor0"
    DefaultDepth    24
    Option         "metamodes" "nvidia-auto-select +0+0 { ForceFullCompositionPipeline = On }"
    SubSection     "Display"
        Depth       24
    EndSubSection
EndSection

```

An alternative to this script, is to create keybinds for the following:

Enable
```
nvidia-settings --assign CurrentMetaMode="nvidia-auto-select +0+0 { 
ForceFullCompositionPipeline 
= On }
```

Disable
```
nvidia-settings --assign CurrentMetaMode="nvidia-auto-select +0+0 { 
ForceFullCompositionPipeline 
= Off }
```


## How to use
Place the script somewhere, and add to your desktop environments startup scripts.

### Mouse input
* left click; enable
* right click; disable
* middle click; exit

