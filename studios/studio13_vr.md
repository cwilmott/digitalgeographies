#Before Class!

### Android Users - Set up Dev Tools on your phone:

To set up developer tools in your phone, follow the instructions below. You need to make sure your phone is also enabled for USB debugging.

**Find your build number**

Firstly, you need to find your build number on your phone. This might be in a variety of places depending on your phone's model and which version of Android you are running.

- Google Pixel: Settings > System > About phone > Build number
- Samsung Galaxy S8 and later: Settings > About phone > Software information > Build number
- LG G6 and later: Settings > About phone > Software info > Build number
- HTC U11 and later: Settings > About > Software information > More > Build number
- OnePlus 5T and later: Settings > About phone > Build number

**Activate developer options**
Once you have found the right place, tap your Build number seven times. After the first few taps, you should see the steps counting down until you unlock the developer options. Once activated, you will see a message that reads, “You are now a developer!”

**Make sure USB debugging is activated**
USB debugging allows you to debug an Android Studio mobile phone application directly through your phone. This setting can be found in the Developer Options menu:

![](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MA0Iz_2G_PFvcDf8T4y%2F-MA0KnOrCgiXcNQKaMyH%2Fimage.png?alt=media&token=d6760d0b-8325-480c-b890-03652bb7d24b)

> If you need further information or guidance on setting up your phone as a dev phone, please go to:  https://developer.android.com/studio/debug/dev-options

### iOS Users - Set up XCode

Developing for iOS is a bit of a pain. For Unity, we're going to build to your phone using XCode. YOU DO NOT NEED TO PAY ANY MONEY.

So, first you'll need to download and install Xcode: https://apps.apple.com/gb/app/xcode/id497799835?mt=12

Now, you need to set up an Apple ID and add it to Xcode.If you don’t yet have an Apple ID, obtain one from the Apple ID site: http://appleid.apple.com/

**Add your Apple ID to Xcode**

Once you have obtained an Apple ID, you must add it to Xcode.
1. Open Xcode.
2. From the menu bar at the top of the screen choose Xcode > Preferences. This will open the Preferences window.
3. Choose Accounts at the top of the window to display information about the Apple IDs that have been added to Xcode.
4. To add your Apple ID, click the plus sign at the bottom left corner and choose Add Apple ID.
![](https://connect-prd-cdn.unity.com/20190130/1fcae2ae-c2d7-4ac7-bd8c-9a590e62db88_add_apple_id.png)
5. A popup will appear, requesting your Apple ID and password. Enter these.
6. Your Apple ID will then appear in the list. Select your Apple ID to see more information about it.
7. Under the heading Team, you will see a list of all Apple Developer Program teams that you are a part of. If you’re using a free 8. Apple ID that isn’t enrolled in the Apple Developer Program, you will see your name followed by "(Personal Team)".
![](https://connect-prd-cdn.unity.com/20190130/7107f562-82a1-48f1-94e0-a6f9aa667616_personal_team.png)

> In the Apple Developer Program, teams are how you organise who has access to a project, what permissions they have and so on. When you use a free Apple ID, Apple creates what is known as a Personal Team for your Apple ID that only has you on it. Don’t worry about it for now - it’s just one of the steps needed to test your app.

# In Class

You made it! Today we build to our phones!

But first, we need to fix up some settings and get it all ready.

1. **plug your phone into your computer with a cable**.
2. Open your Unity project from last week - it should be saved and accessible from within Unity Hub.

## Build Settings!

We're going to diverge a little here, Android and iOS users. Pick your settings, and follow along. I'll be using Android, but I also have an iPhone and sometimes use xCode so we can help with debugging. If there's time, I'll take us through both.

### Android Users

**Build Settings**
1. Navigate to File > Build Settings.
2. Select Android and choose Switch Platform.
3. Select Add Open Scenes and choose HelloCardboard.

**Player Settings**
*Resolution and Presentation*
1. Navigate to Project Settings > Player > Resolution and Presentation.
2. Set the Default Orientation to Landscape Left.
3. Disable Optimized Frame Pacing.

*Other Settings*
1. Navigate to Project Settings > Player > Other Settings.
2. Choose OpenGLES2, or OpenGLES3, or both in Graphics APIs.
3. Select IL2CPP in Scripting Backend.
4. Select desired architectures ARMv7
5. Select Require in Internet Access.
6. At the top, make your "Company Name" "Berkeley"

*Publishing Settings*
1. Navigate to Project Settings > Player > Publishing Settings.
2. Select Custom Main Gradle Template in the Build section.
> Gradle is an Android App Build Module.

**(Left Toolbar at the bottom) XR Plug-in Management Settings**
1. Navigate to Project Settings > XR Plug-in Management.
2. Select Cardboard XR Plugin under Plug-in Providers.

**Add some code to Gradle**
In your Project window, navigate to "Assets/Plugins/Android/mainTemplate.gradle". Double click on mainTemplate.gradle or select Open in the inspector window.

This will open a file of code. Choose Atom as your code editor if you don't already have a default.  

In the code there is a section that looks like this:

```
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
**DEPS**}
```
Add the following lines to the dependencies section of Assets/Plugins/Android/mainTemplate.gradle:

```
  implementation 'com.android.support:appcompat-v7:28.0.0'
  implementation 'com.android.support:support-v4:28.0.0'
  implementation 'com.google.android.gms:play-services-vision:15.0.2'
  implementation 'com.google.protobuf:protobuf-lite:3.0.0'
```
It should look like this:
```
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'com.android.support:appcompat-v7:28.0.0'
    implementation 'com.android.support:support-v4:28.0.0'
    implementation 'com.google.android.gms:play-services-vision:15.0.2'
    implementation 'com.google.protobuf:protobuf-lite:3.0.0'
**DEPS**}
```
Save and close the file.

**Build your project**
1. Navigate to File > Build Settings.
2. Select Build, or choose a device and select Build and Run.

### iOS Users
iOS requires a two stage process - first, exporting the file for iOS, then building using XCode.

**Configuring iOS project settings**
1. Navigate to File > Build Settings.
2. Select iOS and choose Switch Platform.
3. Select Add Open Scenes and choose HelloCardboard.

**Player Settings**
Navigate to Project Settings > Player

Specify your Company domain - call it "Berkeley"

*Resolution and Presentation*
1. Choose > Resolution and Presentation.
2. Set the Default Orientation to Landscape Left.

*Other Settings*
1. Navigate to Project Settings > Player > Other Settings.
2. Disable the Auto Graphics API option.
3. Choose OpenGLES2, or OpenGLES3, or both in Graphics APIs.
4. In Camera Usage Description, write "Cardboard SDK requires camera permission to read the QR code (required to get the encoded device parameters).."
5. In Target minimum iOS Version, write 11.0.
> Note: If using an iPhone X, select the Hide home button on iPhone X option.

**XR Plug-in Management Settings**
Navigate to Project Settings > XR Plug-in Management.
Select Cardboard XR Plugin under Plug-in Providers.

**Build your project**
1. Navigate to File > Build Settings.
2. Select Build or Build and Run.
3. Create a new folder and call it "iOS_Build"

**xCode**
XCode should open automatically. If it doesn't, naviagate to your build .xcodeproj file and open it with XCode.
![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MJMsC8joorFvktc3zx_%2F-MJN9wt91ZZmdaW1Vk3s%2Fimage.png?alt=media&token=32cb06fc-6f25-4ad8-83de-d92dba95ab6c)

1. Select your phone at the top.
2. In Unity-Phone -> General -> Identity, update your Bundle Identifier to match the one you made in Unity. Then, in Signing, select the Team dropdown and select your team that you set up.
![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MJMsC8joorFvktc3zx_%2F-MJNBZDvU9XcfcfAcnp-%2Fimage.png?alt=media&token=f5d53336-c0b8-4dac-86d2-f99f7753464d)

3. If you haven't already, now connect your device to your computer using a USB cable.
> If it’s the first time you’ve connected this device, you may see a message that says that Xcode is "processing symbol files" - this means that Xcode is getting information from the device that will allow you debug apps on this device. Wait for this to complete. Once it has finished processing the symbol files, the message will disappear and your device will be ready to use.

4. The final step before we build to the device is to make sure that your phone is unlocked - it may be worth changing the auto- lock settings to "never" while you're building to the app
5. In the top left of the Xcode interface, click Run (the "play" button).
![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MJMsC8joorFvktc3zx_%2F-MJNC6BsQbkd7odblPMp%2Fimage.png?alt=media&token=5089925a-8bef-44c2-b477-e2a6eed16e2b)

If it works, you should have a notification that appears that says "Build Succeeded".

**Setting Up the App on your iPhone**

The App should open up automatically on your phone, especially if you have the Locative Game already installed. If not, have a look and see if you can see it.

*Untrusted Developer*
You may receive a warning prompt on the device with the title "Untrusted Developer", or a popup in Xcode that says “Could not launch [your app name]”. If you see either of these, it means the that there’s one last step left: you need to set your device to trust your Apple ID.
![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MJNxGieRbELTyhjHDTz%2F-MJRN66X4yulZvTbwun6%2Fimage.png?alt=media&token=3626716d-7672-4e05-b850-b244fda729d2)

This is because you haven't set your phone up as a Development Phone - and your phone isn't trusting this new fangled app thing you're installing not via the App Store.

Select Cancel. Then on your phone tap Settings -> General -> Profiles/Profiles and Device Management/Device Management .

Choose your Developer App account, and then select "trust xxxx.@email.com". You know you're in the right spot when you can see your locative game app beneath the trust button.
![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MJMsC8joorFvktc3zx_%2F-MJNXskrmhq69eP670QZ%2Fimage.png?alt=media&token=acf3c687-7b69-45e0-a083-6a6525d13f5b)

>As long as you have at least one app built using that Apple ID on your device, your device will allow content built with that Apple ID to run. If you ever remove all of the apps built with that Apple ID from your device, you’ll need to go back to this setting and choose to trust it again.

Now, return to your ARProject app and open it again.
