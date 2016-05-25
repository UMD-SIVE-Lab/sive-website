{
  "title": "VRPN and Unreal",
  "description": "A quick guide to using VRPN in an Unreal Project.",
  "date": "2016-05-25",
  "authors": ["beau0307"],
  "projects": []
}

VRPN and Unreal
===============

The VRPN Plugin
---------------

This is a quick overview of how to get started working with VRPN in an Unreal project. I will give you a walk through and give some detail that may specific to the UMD SIVE lab. **This tutorial assumes that you have already compiled VRPN**

First you will need to head over to Reutlingen University VR Lab's website to grab their [VRPN Plugin for Unreal](http://vrlab.reutlingen-university.de/web/858/vrpn-plugin-fuer-die-unreal-engine.html?lang=en).
The download can be found at the bottom of the page or at this link [http://vrlab.reutlingen-university.de/web/wp-content/uploads/2015/07/VrpnPlugin1.zip](http://vrlab.reutlingen-university.de/web/wp-content/uploads/2015/07/VrpnPlugin1.zip).

After unzipping copy the VrpnPlugin folder into your Plugins folder inside your Unreal Project. If it does not exist create it.

You can try to recompile and run however I got some errors.
I had to make a couple of changes to get it compiling

- On line 33 inside the function AVrpnPluginActor::BeginPlay inside VrpnPluginActor.cpp

```
Remove: worldScale = scale;
 Add:    worldScale = GetActorScale3D();
```

- On line 8 of VrpnDelegate.h

```
Remove: #include "VrpnDelegate.generated.h"
```

Using the Plugin
----------------

So now you should have an Unreal Project with the VRPN Plugin compiling.

To use the plugin you can create a new character blueprint or use an existing character blueprint.

- Add VRPN to character
 - Under Component select Add Component.
 - Search for and select VRPN.
- Add the VRPN Interface
 - Select Class Settings from the top menu bar.
 - Under Interfaces, Implemented Interfaces, Select Add.
 - Search for and select VRPN Interface.
- Set VRPN Server IP and Tracker Name
 - Select VRPN Component
 - Enter the VRPN Server IP and Tracker Name.
 - For the current tracker system this would be 192.168.100.200 and PPT0.
- Add Tracker Event
 - Right Click in the blueprint editor
 - Search for and select "Event On Tracker Position"

This event gives three different outputs. The are named "Pos 1", "Pos" and "Rot". Pos 1 is the channel you should probably do a switch statement on this to excute different code for each channel. Pos and Rot are the value that are received from the VRPN server. For the SIVE lab's system we just have the position value. Below is an example of how to use the event in blueprints.

![Blueprint Example](http://vrlab.reutlingen-university.de/web/wp-content/uploads/2015/07/vrpnEvent-example-blueprint.png)

**Note: When using trackers make sure to restart the talking of the VRPN otherwise the tracker number will be stay as the most recently used tracker. This can mess up the data.**

**Note: When using VRPN in combination with the Oculus you must align the axis using the mouse.**
