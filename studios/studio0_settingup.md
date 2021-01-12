# Setting Up

This first studio (on your own!) is basically downloading and installing a bunch of tools and software. If your computer is a little old and sensitive, or doesn't have much space or RAM, I'd recommend holding off on installing Sketch Up and Unity until those respective weeks at the end of the semester. 

List of things to do:
- Sign Up for Github and set up Github Pages. (all)
- Download Google Chrome (all)
- Download Atom code editor (all)
- Install Command Line Tools (Git) (Studio 3-11)
- Install Python (Studio 3-11)

Week Specific Software that we will deal with each week (or check in to see how we're going):
- BitTorrent (Week 9)
- ImageJ (Week 11)
- Sketch-Up (Studio 12)
- Unity (Studio 13)

## Set Up GitHub

The first thing you need to do is set up a GitHub account. GitHub is an industry-standard repository to host your code online, and maintain version control.
Most of the applications we are going to use have GitHub plugins that allow you to 'push' (or send) your code to GitHub and 'pull' (or download) other people's code from GitHub right from your desktop. For these labs, we won't be using any of these features, although once you're more confident, I encourage you to test them out. 
For these labs, we will largely be using GitHub as a place to hold our code and files, and as a web server for web-based applications that we will be making.

### Create a GitHub account

To join GitHub go to: https://github.com and select "Sign Up". Fill in your details and sign up. 

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQcSNyaU8IDTALs_C7%2FScreen%20Shot%202020-06-22%20at%2011.44.30.png?alt=media&token=e0dfb231-78c7-4bd4-8cf4-e4d06cfc961f)

To complete the process, verify your email address.

#### Create a new repository
Now, sign into your new GitHub account. This will take you to your account dashboard.
On the top left of the page, next to Repositories, select "New".

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQdWfMsWUEiJ8mkchM%2Fimage.png?alt=media&token=ed6044ae-775a-4e69-a170-f2b6bac7e018)

Name your repository 'digitalgeographies', set it to **Public** and select the Initalize this repository with a README option. Then select **Creating Repository...**

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQf_VaYn1tz3Gu5GW2%2Fimage.png?alt=media&token=73ab8270-cee0-4ca9-998d-a7386b1af412)

### Set Up GitHub Pages

Finally, once you're in your repository select the "Settings" tab. 

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQiqrERC5NvffPP0ze%2FScreen%20Shot%202020-06-22%20at%2012.07.58.png?alt=media&token=172a7713-0e2a-4eda-b5a3-20be9838eeb8)

Scroll down to GitHub Pages and in Source, select the `master` branch option.

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQixAllIicFvVKO8xw%2FScreen%20Shot%202020-06-22%20at%2012.09.12.png?alt=media&token=d34e4bd6-504d-4246-9efa-d22d11d2788d)

The confirmation screen will show the the web address of your new webpage!

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAML6A6APoKrK7yMGPB%2F-MAQj8kakYLCp3UhHNKN%2FScreen%20Shot%202020-06-22%20at%2012.08.29.png?alt=media&token=09c86d42-666c-4463-800b-3dbd600c26c3)

> If you want to get more into coding, and want to run private projects, UC Berkeley has their own GitHub Server. You can find out more here: https://technology.berkeley.edu/services/web-development-and-hosting-enterprise-applications/github-berkeley 


## Install Atom

In order to write code, it's useful to have a code editor, which will help you by highlighting and colouring your code, organising your files and debugging your scripts.

Android Studio has an embedded text editor. However, Unity does not, and so we need to install one. There are many examples of code editors, each with their pros and cons. It's fine for you to use your preferred text editor or one of these alternatives (https://www.creativebloq.com/advice/best-code-editors), as long as it runs HTML, CSS, Java, Python and C# (c-sharp).

The process for downloading Atom is a little different for each operating system.

#### MacOSX

In your web browser, go to https://atom.io/. Make sure your operating system meets the requirements and then select **"Download"**.

>Atom should automatically detect your operating system, but if it does not, go to https://github.com/atom/atom/releases/tag/v1.48.0 and select the right package.

Once it's downloaded, select the atom-mac.zip and double click. Follow the prompts on the start-up menu to install Atom.

Now, open Atom. In theory, this way of installing Atom will also install the atom and apm commands for use in the Terminal. But it sometimes doesn't work. To make sure, open Terminal and write the following command:
```
$ which atom
```
If the `atom` command has been installed, it will return something like the following:
```
$ which atom
/usr/local/bin/atom
$
```
If the Terminal doesn't return anything, it means that it wasn't installed. To install the atom and apm commands, run "Window: Install Shell Commands" from the Command Palette, which will prompt you for an administrator password. For further guidance see https://flight-manual.atom.io/getting-started/sections/installing-atom/#platform-mac

#### Windows

In your web browser, go to https://atom.io/. Make sure your operating system meets the requirements and then select "Download".

Open `AtomSetup.exe`. This setup program will install Atom, add the `atom` and `apm` commands to your PATH, and create shortcuts on the desktop and in the start menu.

#### Ubuntu (Linux)
You can now install Atom using the Command Line. Open the Command Line and write the following:

```
sudo apt install atom
```

Then make sure you have the latest version
```
sudo apt-get install atom-beta
```
#### Install Packages

Open Atom. In the **Welcome** Guide tab, select the "Install a Package" section. Then click on Open Installer.
This will bring up a dialog box that allows you to search for different add-ons to Atom.

Today, we're going to install two packages: atom_html_preview and turbo javascript

In the search bar write `atom_html_preview` and press the space bar. An option will come up and select "Install". This will install the package.

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAH9VxKlyV8sEFsLeN1%2F-MAHFYzNhmhGXbeTTivq%2Fimage.png?alt=media&token=f393ce30-5094-4f22-ba2a-1c0b68269245)

Next, do the same with `turbo_javascript`.

## Install Unity

The Unity Real-Time Development Platform is an open-source tool which allows developers to add interactivity to 3D environments. It is used as an industry-standard across game development, urban design and planning, and spatial modelling.

You will need to download and install two different components: Unity Hub and Unity.

#### Downloading and Installing Unity Hub
Unity Hub helps you manage which versions of Unity are installed on your computer, as well as which projects you have made.

In your web browser, go to: https://store.unity.com/

Select the Individual Tab, and then Personal.

> As students, you may also choose the Student option, but it requires you to sign up with your .edu email address, and join the GitHub Student Developer Pack.  

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MA26cKvIEqUQMVlBpm1%2F-MA2947QprsV3k13i1NA%2Fimage.png?alt=media&token=fa829de1-9910-4336-876b-184c0c6c3fdd)

Selected **"Get Started"** and click the agreement that you will not be earning more than $100k in funding.
Download Unity 2018.2.14f1 - there are other versions, but this is the only one I've managed to successfully build to my Nexus 5x. Depending on your phone, you might want to try to download other Unity versions.

#### (for Android Users) Add Android Build Support
To use Unity to create a game experience for players on Android, follow these steps:
1. Download and install the Unity Hub.
2. Start the Unity Hub. On the Installs tab, add a version of the Unity Editor that supports 64-bit apps. Note that these versions support Android App Bundles, which enable smaller, more optimized downloads.
![](https://developer.android.com/images/games/unity-hub-add-editor.png)
3. During the installation of the Unity Editor, make sure to include the Android Build Support moduleby checking the box next to it.
4. Expand the Android Build Support module. If you are using Unity 2019 or later, add the Android SDK, NDK and OpenJDK module.


## (iPhone users only) Download and Install Xcode

In the last studio, we're going to be putting a VR app on your phone. iOS is a bit of a pain, and you need to develop through Apple software called Xcode. This should be free - at no point give them any money (they may try to trick you!)

First you'll need to download and install Xcode: https://apps.apple.com/gb/app/xcode/id497799835?mt=12

Now, you need to set up an Apple ID and add it to Xcode.If you don’t yet have an Apple ID, obtain one from the Apple ID site:http://appleid.apple.com/

Once you have obtained an Apple ID, you must add it to Xcode.
1. Open Xcode.
2. From the menu bar at the top of the screen choose Xcode > Preferences. This will open the Preferences window.
3. Choose Accounts at the top of the window to display information about the Apple IDs that have been added to Xcode.
4. To add your Apple ID, click the plus sign at the bottom left corner and choose Add Apple ID.

![](https://connect-prd-cdn.unity.com/20190130/1fcae2ae-c2d7-4ac7-bd8c-9a590e62db88_add_apple_id.png)

5. A popup will appear, requesting your Apple ID and password. Enter these.
6. Your Apple ID will then appear in the list. Select your Apple ID to see more information about it.
7. Under the heading Team, you will see a list of all Apple Developer Program teams that you are a part of. If you’re using a free Apple ID that isn’t enrolled in the Apple Developer Program, you will see your name followed by "(Personal Team)".

![](https://connect-prd-cdn.unity.com/20190130/7107f562-82a1-48f1-94e0-a6f9aa667616_personal_team.png)

In the Apple Developer Program, teams are how you organise who has access to a project, what permissions they have and so on. When you use a free Apple ID, Apple creates what is known as a Personal Team for your Apple ID that only has you on it. Don’t worry about it for now - it’s just one of the steps needed to test your app. More information on managing accounts and teams in Xcode can be found in this Apple documentation.
We will deal with the Unity bit later in the VR studio.
