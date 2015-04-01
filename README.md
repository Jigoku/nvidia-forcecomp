# nvidia-forcecomp
Tray application for toggling changing state of 'ForceFullCompositionPipeline' on nVidia graphics cards.

## Why?
By default, nVidia cards using the blob driver experience tearing. Most notably when scrolling 
applications such as firefox. If ForceFullCompositionPipeline is enabled, the tearing 
dissipates. However, frame rates in OpenGL applications (such as full screen games) tend to 
consume more GPU time. This tray icon allows you to toggle the state on the fly, so if you want 
to browse the web, left click the icon for a tear-free environment. Feel like playing a game? 
Right click the icon before launching it.

## How to use
Place the script somewhere, and add to your desktop environments startup scripts.

### Mouse input
* left click; enable
* right click; disable
* middle click; exit

