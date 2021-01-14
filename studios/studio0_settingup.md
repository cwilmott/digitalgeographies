# Setting Up

This first studio (on your own!) is basically downloading and installing a bunch of tools and software. If your computer is a little old and sensitive, or doesn't have much space or RAM, I'd recommend holding off on installing Sketch Up and Unity until those respective weeks at the end of the semester. 

List of things to do:
- Sign Up for Github and set up Github Pages. (all)
- Download Google Chrome (all)
- Download Atom code editor (all)

Week Specific Software that we will deal with each week (or check in to see how we're going and if our computers have caught fire yet):
- Install Command Line Tools (Git) (Studio 3-11)
- Install Python (Studio 3-11)
- BitTorrent (Week 9)
- Sensors Toolbox app (Week 10)
- ImageJ (Week 11)
- Sketch-Up (Studio 12)
- Unity (Studio 13)
- Xcode (iPhone users only) (Studio 13)

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

