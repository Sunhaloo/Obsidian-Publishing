---
Alias: Microsoft Windows Install
Tag: windows
Author: S.Sunhaloo
Date: 2024-01-03
Status: Completed
---

>[!note]
>If you are smart enough ( *no offence* ), then you already know how to install Windows and also you will know that this can also work for both Windows 10 and Windows 11
>In addition, this is for **me**, the Installation Part I do not really need; I am doing this so that I know how to setup the Programs and how I configure each Program; moreover debloating the shit out of it and making it faster.
>But because, I am writing this, I thought of making a *proper* documentation ( *what is the definition of proper anyway?* )
>- Yeah there will be always things to improve / add, but like I said, I am doing this for **me**, **myself** and **I**

## List of Contents

- [[Windows Reset - Installation#Video Recommendations | Video Recommendations]]
- [[Windows Reset - Installation#Installation Media | Installation Media]]
- [[Windows Reset - Installation#Installing Windows | Installing Windows]]
- [[Windows Reset - Installation#Windows Debloat and Setup | Windows Debloat and Setup]]
- [[Windows Reset - Installation#Windows Settings | Windows Settings]]
- [[Windows Reset - Installation#File Explorer | File Explorer]]
- [[Windows Reset - Installation#Services | Services]]
- [[Windows Reset - Installation#Chris Titus Tech Windows Utility | Chris Titus Tech Windows Utility ( win util )]]

---

- [[Windows Reset - Installation#Programs / Applications / Softwares to Download | Programs / Applications / Softwares to Download]]
- [[Windows Reset - Installation#Settings Up Programs and Games | Settings Up Programs and Games]]

---

### Video Recommendations

- [The only Windows PC optimisation guide you will even need](https://www.youtube.com/watch?v=kIftrmT-PmM) By Khorvie Tech
- [Win Util](https://www.youtube.com/watch?v=KHTuFnVjAuM) By Chris Titus Tech

---

### Where You Can Find Me

- [[Windows Reset - Installation#Socials | Socials]]

---

# Installation Media

>[!note]-
>Chads do not use paid softwares, we pirate and use things that other people pay for free

## Requirements

- Another PC / Computer
- [Windows 10 Installation Media](https://www.microsoft.com/en-us/software-download/windows10)
- USB Drive ( $\ge 8 \ GB$ )

### Creating the Bootable USB Drive

After downloading the *Installation Media*; plug in your USB drive and proceed through the steps.

Depending on the system specification of the *computer* / *device* you are using; It might take a while. On my machine which has:

```

Make | Model : Asus | ROG Strix GL-503VM
CPU: i7-7700HQ CPU @ 2.80GHz
RAM: 16 GB
GPU: GTX 1060

```

It take about 30 mins from starting the Installation Media to unplugging the USB drive.

# Installing Windows

Before turning **on** the computer, plug in the USB drive. After that you can then press the *power button*

>[!warning]
>Depending on what *machine* you have; the keyboard shortcut to enter the **BIOS** might be different.
>On Asus Laptop, the keyboard shortcut to enter the **BIOS** is `F2`; other might be the `F1`, `DEL` key.
>Basically, you need to refer to a YouTube video or better, the manual, because I like documentations.

## Drive Partitions

So... yeah; As I have a 256 GB SSD and a 1 TB Hardrive. I do not need to partition anything and just simply install Windows / any OS on the 256 GB SSD.

For most people, I think that they will only have one drive. Hence, no need to worry about anything. But if you want to make other partition, then you will need to firstly **format** everything and then select the drive that you want to make partitions from and then **input** the amount of *space* you need.

>[!warning]
>If you have a **SSD** ( *Solid State Drive* ). <span style="color: red; background-color: white;">Install Windows <strong><em>on</em></strong> the SSD</span>.
>Installing any OS on the SSD will mean that it will boot up faster.

## Continue Installation Process

After setting up your drives, you can then wait for Windows to *install* on your machine. Then when you are on the ***Toggle Page*** ( *I call it the toggle page, because there are many toggles* ), **TURN EVERYTHING OFF**; because fuck you *Microsoft*. Then be happy and continue!

# Windows Debloat and Setup

## Windows Settings

There are somethings that I do ( *like going into every little settings / toggle and configure them to my liking* ) but I do not think that the person reading this needs to know <span style="color: red"><em>everything</em></span>. This is because I am very *touchy* about settings and toggles ( *if you know what I mean* ).

>Hence, I will be doing what will bring the most performance without major hassle.

>[!note] Note To Myself
>Do Your Thing, Go In Every Settings and Check!!!

### System

#### - Power & Sleep

On the **right** $\rightarrow$; you are going to see ***additional power settings***. Click on it and a *legacy control panel* will open.

##### Choose or customise a power plan

Now, let me get this straight ( *xD* ):

- Laptop $\Rightarrow$ `Balanced`
- PC / Desktop $\Rightarrow$ `High Performance`

Yeah some people will say, yeah if you are a "*gamer gamer*", check the `High Performance` mode even on **Laptops** ( *especially on gaming laptops* ). I do <span style="color: red"><strong>not</strong></span> recommend this. As an aspiring programmer / software developer. I think that, yes; *performance* over everything, but I realised this 3 years ago ( *today is the 3rd of January 2024* ) that **reliability over everything**. I mean it, over **everything**.

<p align="center">You can't play games without a computer; if its fucking broken</p>

The above quote I think is common sense but people if the ( *mostly* ) gaming community will do everything to get better FPS; little do they know that some things are not what they seem to be.

>[!note]
>You can continue to edit the individual settings of each power plan.
>**Future Me**, remember to edit these settings!

##### Define power buttons and turn on password protection

>[!warning]
>On PC / Desktop Computers, you might not have this option, but just search for `Turn on fast startup ( recommended )`, because this is what we are after.

I always turn these type of things **off**. Because I do not trust them. I think that they are actually slowing down your Windows. There are other people that also agree on this. Thus, just turn in **off**.

![[fast-startup.PNG]] $\leftarrow$ See, I have mine on **OFF**

#### - About

On the **right** $\rightarrow$; you are going to see ***Advanced system settings***. Click on it and a *legacy control panel* will open.

##### Advanced system settings

###### Performance Options

- Visual Effects:

	Here you will be able to see 3 options; select the one that says "*Adjust for best performance*"

- Advanced: Processor scheduling

	We do not want our system to provide all of its resources to the Background services. I think the developer at Microsoft did smoke crack before adding this fucking shitty ass feature; like actually why the fuck do you have this option in the first place, don't you think that the performance of should go to the Programs and not the Background services

	*Please check the box for* **Programs**. Thank You.

### Devices

#### - Mouse

On the **right** $\rightarrow$; you are going to see ***Additional mouse options***. Click on it and a *legacy control panel* will open.

>[!tip]-
>You can also open this exact legacy settings page by opening the Run Box with the shortcut `Ctrl + R` and typing `main.cpl`.

##### Additional mouse options

###### Pointer Options

- Motion:

	I like it bring the slider all the way to the left and then use the keyboard ( *move the slider with the arrow keys* ) and count to 6.

	For the love of God; **PLEASE TURN OFF `Enhance pointer precision`**. This is basically *Mouse Acceleration*

	$$Enhance \ pointer \ precision \Rightarrow Mouse \ acceleration$$

You can leave the other settings as it is.

- I like to use Custom Pointers like:

	1. Numix Cursor
	2. Bibata Cursor
	3. Adwaita Cursor

	You can usually find these on DeviantArt and GitHub

#### - Typing

Here is an image of how *I* like to setup this section

![[settings-keyboard_settings.PNG]]

But there is one more thing that I can make the *keypresses* fasters and that is done by using an *in-built* program called "*Keyboard Properties*"

##### Steps:

- Open the Run Box using `Ctrl + R`
- Type `control keyboard` and press enter

Now set-up the sliders as show below:

![[control keyboard-sliders.PNG]]

This will make the keypresses faster if your keyboard does not have a software. Nevertheless, even if your keyboard has a software; I still recommend performing this small step.

>[!note]
>You can leave the `Cursor Blink Rate` as it is. I am used to using the terminal without it blinking.

### Network & Internet

#### - Status

##### Advanced network settings

Click on `Change adapter options` and the legacy control panel will open up.

>[!warning] Configuring Ethernet Only
>I will only be writing about configuring the **Ethernet** adapter properties only.
>>[!note]-
>I think that you should **firstly** update your Internet Driver. It might be *Realtek* or *Intel* or whatever.
>I have never tested this; but I think that if you perform all the steps that I have mention and then you update. I think that it might revert back to the original settings.
>Again, I never tested this, but just go online and update it manually.

Remember the Khorvie Tech guy from the [[Windows Reset - Installation#Video Recommendations | Video Recommendations]] from above. Instead of me explaining this part; better that he shows you how to configure them in this video right [here](https://www.youtube.com/watch?v=kIftrmT-PmM&t=1103s)

>Good I do not need to type much them. Thank *YouTube University*

### Apps

#### - Apps & features

##### Apps & features

>[!bug] DELETE ALL SHITTY SOFTWARES
>This can include things like:
>- OneDrive
>- Skype
>- Help
>- Camera
>- Other shites
>>[!warning]
>>Now don't go delete things like *Drivers* and other crucial stuff

Now you will have to do a very boring and repetitive task. After deleting all of the other crap; you will now have to go in every application / program and turn **off**

- Background Apps
- Any other permission like Camera or Microphone
- Runs at login

>I know that there is a way of turning off *Background Apps* in another section. But as I am already there; I make sure that it is actually off.

#### - Startup

##### Startup Apps

>[!Bug] Just Turn Everything OFF
>We do not need programs to start when our computer is starting
>If I want to use a program then I will open it myself.
>This will massively decrease the boot-up time if you had many startup apps turning on or if you are using a hard drive.

### Gaming

#### - Game Bar

>[!Bug] Turn it OFF
>1. We do not give a fuck about game bar
>2. It just makes a worst gaming experience and more laggy

#### - Game Mode

Okay, so the toggle `Game Mode` depends... What I mean by "*depends*" it that not every machine is the same. Right now I have it turned on and more and more people are seeing improvement to performance while this toggle is switched to on. But I had a computer that did **not** perform well with this setting and it was an old, I mean *OLD* computer.

Right now with the my laptop ( *see specifications down below $\downarrow$* ), I can use it.

```

Make | Model: Asus | ROG Strix GL-503VM
CPU: Intel(R) Core(TM) i7-7700HQ CPU @ 2.80GHz
GPU: Nvidia GTX 1060 ( 6GB GDDR5 )
RAM: 16 GB

```

##### Graphics Settings

On the **right** $\rightarrow$; you are going to see ***Graphics settings***. Click on it and it will take you to another page.

- Hardware-accelerated GPU scheduling

	I have this turned **on**; but is is the same story as above $\uparrow$

### Privacy

I will be skipping this, because it will be a waste of my time and your time to read all of this. Just remember go into each settings and read carefully then make a decision on where to turn *on* or *off* something / feature. If you ever feel stuck; just remember we still have Google, YouTube, ChatGPT.

### Update and Security

>I just want to say that Microsoft / Windows stinks at updates ( *I think everybody know that and agrees* ).

#### - Windows Update

After updating, press `Pause updates for 7 days`. Click on it until you cannot click it anymore.

- Why are we doing this?

	This is so that *updates* do not occur in the background while we are using the computer, because it uses a lot of computer resources.

But whenever you feel like the computer is *slowing* down; then click on `Resume Updates`. Remember to pause the updates again after updating.

##### Advanced options

Right below you are going to see `Advanced options` from the same page. Click on it and it will bring you to another page.

- Update Options

	I have it setup like in the image below $\downarrow$

	![[windows update-advance options.PNG]]

## File Explorer

I will be quick with this one. Go on and open **File Explorer** and find `This PC`. You will be able to see that you are in the correct place if you can see your drives.

Now **right-click** on the one drive and hit *Properties*. Under the **General Tab**, the last thing there should be something like `Allow files on this drive to have contents indexed in addition to file properties`

- Turn it **off**

	![[hard drive-indexing.PNG]]

- Repeat for other drives / partitions

>Depending on your system, and amount of files that you have; it might take a while, so be patient.

## Services

There are 2 ways which I know how to open the services window.

- First Method: Using the Run Box
	- Again press `Ctrl + R`, this will bring up the Run Box
	- Then type `services.msc`
- Second Method: Using Task Manager
	- Press `Ctrl + Shift + ESC`
	- And go to the `services` tab

Again I recommend that you watch the video by Khorvie Tech. The [video](https://www.youtube.com/watch?v=kIftrmT-PmM&t=115s) will show you what to disable.

## Chris Titus Tech Windows Utility

In my Windows Journey; I think that this is one of the best pieces of software that have been created for Windows optimisation people like me.

To use this *software*, we need to use Powershell ( *I like using the terminal for most things even programming with Neovim - check out my [dotfiles](https://www.github.com/Sunhaloo/dotfiles)* )

### Steps:

- Open Powershell
- Then type:
	```
	iwr -useb https://christitus.com/win | iex
	```

Once the program / application pulls up click on the `Tweaks` tab and I do not know what level of computer intelligence you are in your life; So just do `Minimal` or `Laptop` if you are on laptop. Once you are done click on the `Run Tweaks` button

>[!note]
>This is a safe program, no need to worry about crashing or viruses. The project is on [GitHub](https://github.com/ChrisTitusTech/winutil)

## Temporary and Prefetch Folder

### Temporary Folder

To access the temporary folder, open the Run Box again using the shortcut `Ctrl + R` ( *there is another way to open this folder through the File Explorer; but it is slower* ). Type the following in the Run Box

```

%localappdata%

```

After pressing `Enter`; a File Explorer will open and then you need to find the `Temp` folder. Then you can right click on it and create a desktop shortcut.

Basically, all programs have temporary files that will be created when they are opened. It the accumulated in the `Temp` folder. Some people's `Temp` folder are 10GB in size. Hence, it is necessary to **delete** all the files in it from time to time so that the computer does not slow down and also "*free space*".

### Prefetch Folder

To access the "*prefetch*" folder; you will need to go to this location in your File Explorer:

```powershell

C:\Windows

```

>If you do not understand this, firstly what the fuck and secondly you need to learn it as it is very simple to understand. But for now just Google it.

Again, this is similar to the `Temp` folder, we just need to delete the contents from time to time.

## Windows Features

>[!note] You can skip this step if you are not a Programmer or do not use things like Virtualisation

Search for `Turn Windows features on or off`

Use the image below $\downarrow$ as a guide

![[Windows Features.PNG]]

>[!note] Note to self
>If you are going to use VMs; remember to turn it on.

# Programs / Applications / Softwares to Download

>[!note]
>As I said from the beginning; I am doing this "*documentation*" for me, myself and I. I do not expect you to download the same things that I use. But there are some interesting software that you can take a look.
>There are hyperlink; so you can click on them and they will send you to their corresponding website.

## Utilities

- [Firefox](https://www.mozilla.org/en-US/firefox/new/) - Because I am planning to switch to Linux and Linux people use Firefox
- [Geek Uninstaller](https://geekuninstaller.com/download) - I do not use the uninstaller from the Windows Settings ( *Download the portable version* )
- Mouse Drivers:
	- [Cooler MasterPlus](https://masterplus.coolermaster.com/)
	For now I only have a Cooler Master MM710; If you have a mouse that can be configured using a software; go and download it.
- [Open Broadcasting Software (OBS)](https://obsproject.com/download) - For Recording and Streaming
- Nvidia Control Panel - If it has not come pre-installed, you can download if from the Microsoft Store or Internet
- [Nvidia GeForce Experience](https://www.nvidia.com/en-us/geforce/geforce-experience/) - For updating Nvidia Drivers
- New Terminal - From the Microsoft Store
- New Powershell - From the Microsoft Store
- Equaliser APO - Used for Audio
- 7 Zip- Download through terminal with Scoop

## Work

- [Obsidian](https://www.obsidian.md) - The best note taking application I think that exists on the planet.
	This very documentation is being written in Obsidian
	![[windows docs using obsidian.png]]
	It is blurry as I use `1600 x 1024` resolution; I do not use Native Resolution.
- [VS Code](https://code.visualstudio.com/download) - The Standard of Editors, but I am trying to use Neovim now ( *even if you are not a programmer; I recommend installing it* )
- [Python](https://www.python.org/downloads/) - The Python Interpreter

## Entertainment

### Songs

- [Spotify](https://www.spotify.com/us/download/windows/)

### Games

#### Steam

- Aimlabs
- BattleBit Remastered
- HudSight

#### Epic Games

- Fortnite

#### Minecraft Launcher

- Minecraft

#### Other

- Roblox ( with [RobloxFPS Unlocker](https://github.com/axstin/rbxfpsunlocker/releases) )
- Live For Speed
- Need For Speed

# Settings Up Programs and Games

## Mouse Software

>[!note]
>Whatever mouse you have ( *that have a software* ); I like to setup my mouse like this

```

DPI: 1600
Polling Rate: 1000 Hz
Debounce Delay: As low as possible
Angle Snapping: OFF

```

>Optimum Tech has a good [video](https://www.youtube.com/watch?v=imYBTj2RXFs) on why we should use *1600 DPI*

### Visual Studio Code

#### Settings ( *Normal Settings* accessed by pressing `Ctrl + ,` )

- Editor: Font Size = 16
- Editor: Font Family = Agave Nerd Font Mono, PlemolJP35 Console NF, Consolas, 'Courier New', monospace
	>You might be wondering; "*What the actual fuck?*"; I like to switch things often.
- Editor: Tap Size = 4
- Editor: Cursor Style = line
- Editor: Word Wrap = off
- Editor: Mouse Wheel Zoom = on
- Window: Zoom Level = 1

#### User Settings `.json` File

Here is a look at my User Settings JSON File

```json

{

    "workbench.colorTheme": "One Dark Pro",
    "workbench.colorCustomizations": {

        // Cursor Colour = White
        // "editorCursor.foreground": "#ffffff",
        // Cursor Colour = Lime Green
        "editorCursor.foreground": "#b1ee46",
        // Cursor ( Terminal ) Colour = White
        // "terminalCursor.foreground": "#ffffff",
        // Cursor ( Terminal ) Colour = Lime Green
        "terminalCursor.foreground": "#b1ee46",

    },

    "editor.fontSize": 16,
    "editor.mouseWheelZoom": true,
    "editor.minimap.enabled": false,
    "workbench.startupEditor": "none",
    "explorer.confirmDelete": false,
    "workbench.iconTheme": "material-icon-theme",
    "editor.fontFamily": "Agave Nerd Font Mono, PlemolJP35 Console NF, Consolas, 'Courier New', monospace",
    "liveServer.settings.donotShowInfoMsg": true,
    "window.zoomLevel": 1,
    "explorer.confirmDragAndDrop": false,
    "liveServer.settings.donotVerifyTags": true,

}

```

#### Extensions

Below $\downarrow$ you will find a list of all the extension that I use.

Themes:

- Solarised Osaka by Hayden Ngo
- One Dark Pro by binaryify - My **Main Theme**
- Tokyo Night by enkia
- Material Icon Theme by Philipp Kief

Tools:

- Vim by vscodevim - Vim Motions
- WSL by Microsoft - Windows Subsystem for Linux
- Live Server by Ritwick Dey - HTML Tools

Programming:

- Python by Microsoft
- Pylance by Microsoft
- C/C++ by Microsoft
- C/C++ Extension Pack by Microsoft
- CMake Tools by Microsoft
- CMake by twxs
- Code Runner by Jun Han

## Terminal

### Terminal Settings

>[!note]
>On Windows 11, we already have the new Terminal pre-installed

After downloading the *new* Terminal and Powershell 2.0 from the Microsoft; we can now start it.

Open the settings using `Ctrl + ,` or like a peasant that use the mouse ( *we like mouseless development / experience here* )

#### Startup

- Default Profile: Powershell 2.0
- Default terminal application: *The new terminal that we are using*
- Launch on machine startup: off
- When Terminal starts: Open a tab with default profile
- New instance behaviour: Create a new Window
- Launch size:
	- Columns = 120
	- Rows = 30
- Launch parameters: Default, Let Windows decide, Centered

#### Interaction

- Automatically copy selection to clipboard: off
- Text formats to copy to the clipboard: Plain text only
- Remove trailing white-space in rectangular selection: on
- Remove trailing white-space when pasting: on
- Snap window resizing to character grid: on
- Tab switcher interface style: Separate window, in tab strip order
- Automatically focus pane on mouse hover: off
- Automatically detect URLs and make them clickable: On
- Warn when closing more than one tab: on

#### Appearance

- Application Theme: Dark
- Position of newly created tabs: After the last tab
- Hide the title bar: on
- User acrylic material in the tab row: on
- Always on top: off
- Tab width mode: Equal
- Pane animations: off
- Always display an icon in the notification area: off
- Hide Terminal in the notification area when it is minimised: off
- Automatically hide window: off

#### Rendering

- Everything should be turned **OFF**

#### Defaults

- Starting directory: *I like it to be on the Desktop*
- Run this profile as Administrator: off

Additional Settings:

##### Appearance

Text:

- Colour scheme: One Half Dark
- Font Face: *Depends on my mood*, but use Hack Nerd Font
- Font Face: *From 16 to 17*
- Line height: 1.2
- Font weight: Normal
- Retro terminal effects: off
- Automatically adjust lightness of indistinguable text: Never

Cursor:

- Cursor Shape: Filled Box

Background Image:

- If you want to use background image; choose from the File Explorer and be happy
- You can also change the image opacity with `Background image opacity`

>You can find cool wallpapers on [Wallhaven](https://www.wallhaven.cc)

Text Formatting:

- Intense text style: Bright colours

Transparency:

- If you want the terminal to be transparent; change the `Background Opacity`
- You can also turn on `Enable acrylic material` if you want to

Window:

- Padding: 8
- Scrollbar visibility: Hidden

>[!tip] `settings.json` File
>My `settings.json` file is found on my GitHub [dotfiles](https://www.github.com/Sunhaloo/dotfiles) under the folder `windows-terminal settings`

### Configuring Terminal Program ( *using CLI* )

Firstly we will need to install [Scoop](https://scoop.sh/). It is a [package manager](https://en.wikipedia.org/wiki/Package_manager) for Windows. There is also [Choco](https://chocolatey.org) which is available; I prefer Scoop.

Go to the website and copy the installation command.

>I have not added to installation command here; even though it will never change, I have a feeling that it might change.

#### Scoop Post Install

The very first command that you **need** to know is

```powershell

scoop help

```

$\uparrow$ This will show all the list of *arguments* that is available.

##### Updating Scoop

```powershell

scoop update

```

Not only it update Scoop itself, but also the programs that we have installed using Scoop

##### Installing CLI Programs

For Example if we want to install *Neovim*; we would do:

```powershell

scoop install neovim

```

Here are some apps / program that I usually installed:

1. Git - *I mean does this need and explanation*
2. Neovim - Main Editor ( *yes, Neovim is and EDITOR* )
3. 7zip - To Extract Folders / Files
4. ffmpeg
5. [yt-dlp](https://github.com/yt-dlp/yt-dlp) - Tool I used to convert YouTube videos to audio format
6. gcc - Compile C / C++ programs

##### List CLI Program

To list all of your installed apps / programs; do:

```powershell

scoop list

```

### Neovim

Now that we need to do to configure Neovim to my liking is to **clone** my [dotfiles repository](https://www.github.com/Sunhaloo/dotfiles).

In the terminal navigate to the Desktop Folder. Use the command below to clone my dotfiles repo:

```poweshell

git clone https://www.github.com/Sunhaloo/dotfiles

```

After running this command a folder with the name `dotfiles` will appear.

Now we are going to be using the Run Box again; open the Run Box using the shortcut `Ctrl + R` and type `%localappdata%` and hit `Enter`.

Now we are going to **move** the `nvim` folder found in the `dotfiles` folder to `C:\Users\your_username\AppData\Local` ( *the fucking folder that we just opened with the Run Box* )

>[!success]
>If we go back to the terminal ( *one more thing; the things that I did above $\uparrow$ can be done through the Terminal* ) and type `nvim` and see the glorious Neovim Editor come to life with [Lazy](https://github.com/folke/lazy.nvim)

## Obsidian

Ahh yes, **THE** best note taking app for **me**. Remember the `dotfiles` folder? Yeah so there is my `.obsidian` folder in the `obsidian_dotfiles` folder.

Copy that folder into the folder that you want to use as a vault. That's it.

>Now I will be still configuring everything in the Settings Page

## OBS Studio

### General

#### General

- Theme: Dark

#### Source Alignment Snapping

- Snap Sensitivity: 10.0
- Snap Sources to edge of screen: ON
- Snap Sources to other sources: ON

### Stream

- Service: YouTube - RTMPS
- Server: Primary YouTube ingest server

### Output

Set the `Output Mode` to `Advanced`

---

- On The **Streaming** Tab

#### Streaming Settings

- Audio Encoder: FFmpeg AAC
- Video Encoder: Nvidia NVENC H.264
- Rescale Output: OFF

#### Encoder Settings

- Rate Control: CBR
- Bitrate: 7000 Kbps
- Keyframe Interval ( 0=auto ): 0 s
- Preset: P3: Fast ( Low Quality )
- Tuning: Ultra Low Latency
- Multipass Mode: Two Passes ( Quarter Resolution )
- Profile: high
- Look-ahead: OFF
- Psycho Visual Tuning: ON
- GPU: 0
- Max B-frames: 2

---

- On The **Recording** Tab

The `Type` should be on `Standard`

#### Recording Settings

- Recording Path: Depends
	- Generate File Name without Space: OFF
- Recording Format Matroska Video ( .mkv )
- Video Encoder: ( Use Stream Encoder )
- Audio Track: 1
- Custom Muxer Settings: *Leave Blank*
- Automatic File Splitting: OFF

>Leave the other tabs as it is.

### Audio

#### General

- Sample Rate: 48 kHz
- Channels: Stereo

#### Meters

- Decay Rate: Fast
- Peak Meter Type: Sample Peak

### Video

- Base ( Canvas ) Resolution: *Will add depending on what resolution I will be using*
- Output ( Scaled ) Resolution: `1980 x 1080`
- Downscale Filter: Bicubic ( Sharpened scaling, 16 samples )
- Common FPS Values: 60

### Hotkeys

#### Mic / Aux

- Mute: `Ctrl + M`
- Unmute: `Ctrl + Shift + M`

## Equaliser APO

My config file for Equaliser APO is:

```

Include: Headset.txt
Preamp: 0 db
Copy: L=R R=L

```

>[!note]
>My Asus Laptop switches the stereo by itself. This means that my left is right and vice versa. Hence, this is why I used Equaliser APO to switch it back. You do not need the line `Copy: L=R R=L` if your stereo is good out of the box.

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!