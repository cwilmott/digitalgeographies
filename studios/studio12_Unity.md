
# Before Class!

## Download UnityHUB

Then, you need to download the Unity install version 2020.3.1, and make sure you include the "build tools" for the mobile phone platform you have (Android or iOS). For more info, see here https://app.gitbook.com/@clancy-wilmott/s/locative-media/lab-1/setting-up-your-mixed-reality-development-environment/setting-up-unity (but note, we are installing the 2020 version, not the 2018 version)

## Download Github Desktop

Finally, you shoud have git installed already on your computer, but just in case, install GitHub Desktop: https://github.com/git-guides/install-git#:~:text=Install%20Git%20Using%20GitHub%20Desktop,simple%20collaboration%20tool%20for%20Git.




# In Class

## Create a new project.
Open up Unity Hub and create a new Unity 2020.3.1 project, choosing the 3D template on the left (download it if it doesn't come up). We will use this next week when we export. Then click "Create Project"

## Unity

Unity is a game engine, designed for adding interaction between elements. It's halfway between film editing software and a coding suite. There are often multiple ways of achieving what you want in Unity - sometimes using code, sometimes without. Many game studios use Unity as a basis for their game design.

What we're doing today is working with the Cardboard SDK for Unity, which brings in cross-reality (XR) and virtual reality (VR) capabilities to your game (i.e. it sets up your space for viewing).

Unity takes a bit of getting used to it if you're not familiar with the interface. Stick to what you feel comfortable doing, and just play around - and I often find video tutorials are easier when starting out in Unity, since there are so many windows and so many drag options.

### The Unity interface

Hello windows!

The Unity Interface has lots of movable windows and options for customisation. Your layout might look different to mine - if you can't find the right window, check the tabs and or go to Window -> General in the top menu and you'll find the list there.

These windows float around and can be rearranged according to your own preferences. For this reason, it's important to get to know what each of them does, and what they're called, since they will help you navigate the rest of the tutorial.

**Hierarchy**
The hierarchy window shows the file structure of your current scene(s). Main Camera is the view from which your game is played, and Directional Light provides shadowing and light. LocationBasedGame is where all the Mapbox functions are, including the map, the player icon (which changes with your location) and the location provider which

**Inspector**
This shows the details of the objects in your hierarchy. It is where you add components and scripts, where you change the position and layout of objects, and how you change the name of an object.

**Game**
This window is a preview of what your game will look like. You use this screen to test your game when you're in play mode.

**Project**
This is where all the assets for your project are. To add them to your project, drag them into the hierarchy.

**Scene**
This is an editable space where you can see a spatial overview of all the objects in the game and how they relate to each other.


## Import Cardboard SDK

1. In Unity, go to **Window > Package Manager**.
2. Click + and select Add package from git URL.
3. Paste https://github.com/googlevr/cardboard-xr-plugin.git into the text entry field. (You MUST have Git installed here - if it doesn't work make sure you have downloaded GitHub desktop. Mac Users may need to install command line tools depending on their OS)
4. The package should be added to the installed packages.
5. In the left side bar of the package manager, navigate to the Google Cardboard XR Plugin for Unity package. In the Samples section, choose Import into Project. (Sometimes an error can appear, but check your asset folder before worrying too much)
6. In the Project window, the sample assets should be loaded into **Assets/Samples/Google Cardboard/<version>/Hello Cardboard/Assets**.
7. Navigate to Assets/Samples/Google Cardboard/<version>/Hello Cardboard/Assets/Scenes, select **HelloCardboard** and drag it into the Hierarchy window.

## Take a look at your victory prefab.

Hopefully, you have a prefab that looks like some nice coloured blocks: "Cube Room"
In the hierachy, take a look at the different objects. What do you think they do? To test your game, select the "Play" button at the top or look in the game view window.

Depending on your confidence, have a play around with the Treasure objects - or just have a closer look at their attributes.  


## Import some files.

The world of CAD is insane when it comes to file types. There are SO MANY different programs on the market, with different capabilities. To keep it simple, we're importing a obj because I personally find it the least frustrating object to import without losing the materials.

1. Download the OBJ, MTL and JPG files onto your desktop.

2. To import an object, select it and drag it into the Assets folder. Select all three files and drag them into the assets file. Alternatively, select "Assets - > Import New Asset"

3. something should appear in the assets folder in the project window.


> **For your future creations!**
>
> As part of the University, we have free access to the AutoCAD suite, but it's not always the most intuitive option. Some example workflows for browser based apps to Unity:
>
> 1. Sketch-Up online -> export as STL / Open in TinkerCAD -> export as OBJ / Open in Unity
> 2. Clara.io -> export as FBX / Open in Unity
> 3. TinkerCAD -> export as OBJ / Open in Unity
>
> *Other downloadable apps that can export .dae or .fbx:*
> 1. Blender is an excellent option
> 2. AutoCAD desktop
> 3. SketchUp Free Trial

## Add them to the scene.

Drag the .obj file into the Cube Room folder in the hierarchy. Delete the Cube Room prefab if you'd like.

## HAVE FUN!
