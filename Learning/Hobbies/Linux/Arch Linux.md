---
Alias: Arch Linux Setup
Tag: linux, arch
Author: S.Sunhaloo
Date: 2023-01-17
Status: HOLD
---

>[!warning]
>EFI Install Guide

## List of Contents

### Installing Arch

- [[Arch Linux#Basic Installation | Basic Installation]]
- [[Arch Linux#Requirements | Requirements]]
- [[Arch Linux#Installation Process | Installation Process]]
- [[Arch Linux#[Install Base System](https //www.youtube.com/watch?v=68z11VAYMS8&t=480s) | Install Base System]]
- [[Arch Linux#Entering our Installed System | Entering our Installed System]]
- [[Arch Linux#[Adding A User](https //www.youtube.com/watch?v=68z11VAYMS8&t=867s)| Adding A User]]
- [[Arch Linux#Setting up our Boot Loader ( GRUB ) | Setting up our Boot Loader ( GRUB )]]

---

- [[Arch Linux#[Arch Linux Post Install Guide](https //www.youtube.com/watch?v=YPrhIfm3VJs) | Arch Install Post Guide by Mashed]]

---

- [[Arch Linux#Installing KDE Plasma ( Desktop Environment ) | Installing KDE Plasma ( Desktop Environment )]]
- [[Arch Linux#Start Linux Desktop | Start Linux Desktop]]

### Setting Up The Desktop Environment

---

# Basic Installation

>[!note]
>This means that the basic of basic; minimal installation with a desktop environment ( *I prefer KDE Plasma* ) and some basic applications like *Firefox*, *Konsole* or *Kitty* or some other shit.

There are many ways to install Arch Linux and if you are a beginner like me then the easiest way to get started is using the **[official guide](https://wiki.archlinux.org/title/installation_guide)** and some **YouTube** videos.

### Some YouTube Video Recommendations

1. [Arch Linux: A Comfy Install Guide by Denshi](https://www.youtube.com/watch?v=68z11VAYMS8)

>[!note]
>As from now, I will be following this tutorial $\uparrow$.

## Requirements

You will need:

- [Arch Linux ISO File](https://archlinux.org/download/) $\rightarrow$ The actual OS
	- Select your region to get the fastest download speed.
- [Rufus](https://rufus.ie/en/) $\rightarrow$ To burn our ISO file to a pendrive

## Installation Process

Run this command first and foremost:

```bash

reflector --latest 20 --protocol https --sort rate --save /etc/pacman.d/mirrorlist

```

You can use `Tab` to complete commands.

**What does the above command do?**

It allow for faster download speed of packages

### Configure Keyboard Layout and Font

#### Keyboard Layout

Here are some common keyboard layout commands:

1. US Layout ( *my choice - even on UK layout keyboards* )

```bash

loadkeys us

```

2. UK Layout

```bash

loadkeys uk

```

>[!note]-
>The **default** keyboard layout is *US*!
>>Very Nice! I do not have to change anything

#### Fonts

To change default fonts if it is too small on your screen you can use the command:

```bash

setfont

```

All the fonts are located in `/usr/share/kbd/consolefonts/`. Hence you can set the font using the template below

```bash

setfont insert-name-font-here

```

### Connecting to the Internet

First of all, if you are on **desktop**, you probably are using an *Ethernet* cable and you should be good to go. But if you are connected using WiFi ( *either using a Wireless Adapter of Desktop or on Laptop* ).

You will then need to run the command:

```bash

iwctl

```

>[!warning]
>I will not be covering this part; search it up yourself, I already have an *Ethernet* cable plugged in and ready to go.

#### How to check Internet Connection

It is very simple to check if you are connected / online.

You can run the command:

```bash

ping www.google.com

```

- or use any other website you want

I like to ping cloud fare's servers, which is

```bash

ping 1.1.1.1

```

>[!note]
>Use `Ctrl + C` to stop the "*checking of the connection*"

### Partitions / Drive Selection

To see all of your drives and other partitions use the command:

```bash

lsblk

```

The guide recommend you to use `fdisk`. But I will go with the [video](https://www.youtube.com/watch?v=68z11VAYMS8&t=180s) which recommends using `cfdisk`.

>Follow the video to see how to partition your Drives

>[!note]
>Partitions to be created
>- EFI / Boot Partition
>- Swap Partition
>- Root Partition ( *the place where our file actually lives* )

### Format Partitions / Drives

After you have partitioned your drives, you can now proceed to format and initialise them.

#### Root Partition

```bash

mkfs.ext4 /dev/root_partition

```

#### Boot Partition

```bash

mkfs.fat -F 32 /def/efi_system_parition

```

#### Swap Partition

```bash

mkswap /dev/swap_partition

```

### Mount Partitions

#### Mount Root Partition

Start with the root partition to make thing easier for ourselves

```bash

mount /dev/root_partition /mnt

```

#### Mount Boot Partition

We need to mount our **boot** partition in the `/mnt/boot/efi` folder, which currently does not exists

Thus we need to make it using the command:

```bash

mkdir -p /mnt/boot/efi

```

Then we can mount our root partition there, using the command below:

```bash

mount /dev/boot_partition /mnt/boot/efi

```

>[!note]
>In the Official Arch Linux Guide, they do it like this:
>```bash
>
>mount --mkdir /dev/boot_partition /mnt/boot
>
>```
>> I have never tried this, I do not know that if it will work; it should!

#### Turn Swap Partition On

```bash

swapon /dev/swap_partition

```


### [Install Base System](https://www.youtube.com/watch?v=68z11VAYMS8&t=480s)

You will need to run the command:

```bash

pacstrap /mnt/ base linux linux-firmware sof-firmware base-devel grub efibootmgr vim nano networkmanager

```

### Configure System

#### Fstab

I will suggest watching the [video](https://www.youtube.com/watch?v=68z11VAYMS8&t=580s) because it will do a better job at explaining it


If you run `genfstab /mnt` you are going to get an output of your **file system** that you created like our:

1. Root
2. Boot
3. Swap

But we want those things / output in our **disk**; not on the terminal. So we proceed by writing this command:

```bash

genfstab /mnt > /mnt/etc/fstab

```

We can verify the contents of this files by using `cat`. Hence,

```bash

cat /mnt/etc/fstab

```

>It should have the same content like we did for the same command

### Entering our Installed System

#### Arch Root User

Use the command below to enter the root / admin of Arch Linux, then we will proceed with other things such as creating a user account and stuff.

```bash

arch-chroot /mnt

```

#### Set Up Time Zone

```bash

ln -sf /usr/share/zoneinfo/Continent/Country /etc/localtime

```

>[!warning]
>Change `Continent` and `Country` to your specific country.
>- You can use `Tab` to autocomplete it.

To verify if your time is set correctly, run the command `date`.

#### Synchronising System Clock

To sync our system clock, use the command below:

```bash

hwclock --systohc

```

#### Localisation

Again this [video](https://www.youtube.com/watch?v=68z11VAYMS8&t=710s) explains it so much better than me; hence I will only be writing the commands that he used. In addition, I am using the same *locale* as him.

Go to the file and we need to remove the comment ( *like remove the symbol `#` in front of what you are going to be using as your locale*)

>You can use whatever text editor you want!
>- Either nano or vim ( *CHADS use Vim, Remember!!!* )

```bash

vim /etc/locale.gen

```

Now find `en_US.UTF-8 UTF-8` and remove the `#` symbol. Save and quit the file.

We can verify it by using the command:

```bash

locale-gen

```

We also need to specify our locale in `locale.conf` found in `/etc/locale.conf`, again:

```bash

vim locale.conf

```

Type the following into that file:

```bash

LANG=en_US.UTF-8

```

>Remember to save and quit.

#### Host Name ( Computer's Name )

To give the computer / Arch computer a name we need to go to `/etc/hostname` and use our text editor ( *Vim, again because CHADs use Vim* ).

```bash

WhateverYouWantYouComputerToBeNamed

```

- Save and quit

#### Root Password

Similar to changing passwords on Linux / Termux, use the command:

```bash

passwd

```

Then you can enter your root password.

### [Adding A User](https://www.youtube.com/watch?v=68z11VAYMS8&t=867s)

We are now going to be adding your User thing, like the user in Windows and Mac. You know what I mean. *FUCK YOU*!

To add a user use the ( *several commands that will be written* ) command below:

```bash

useradd -m -G wheel -S /bin/bash UserName

```

>Where `UserName` is our User Name.

#### Create a Password for User *Account*

So we can create a password for the User Account by using:

```bash

passwd UserName

```

>Again, where `UserName` is your User Name.

#### Setup `Sudo`

To be able to run `Sudo` commands in our *Account*. We need to do the following:

```bash

EDITOR=vim visudo

```

>Our you can use `nano` for the `EDITOR`. Remember CHADs use Vim.

Now find `wheel ALL=(ALL) ALL` and **uncomment it** by removing the `#` symbol. Save and quit.

We can verify if we have `Sudo` permission by entering our *Account* using `su UserName` ( *where `UserName` is your User Name* ) and run a command like Update the system, i.e, `sudo pacman -Syu`.

#### Enable Network Manager

To enable the Network Manager, we can run the command:

```bash

systemctl enable NetworkManager

```

### Setting up our Boot Loader ( GRUB )

<p style="color: orange;">When I was setting up Arch, I had some problem with this step which required me to user <code>-- Force</code> in one of these commands.</p>

```bash

grub-install /dev/sda

```

Configure GRUB ( *the part where I got some problems where It would not configure* )

1. Try this First

```bash

grub-mkconfig -o /boot/grub/grub.cfg

```

2. If it does not work, use this command instead:

```bash

grub-mkconfig -o /boot/grub/grub.cfg --Force

```

### Finishing Touches Before Installing Our Desktop Environment

After we have finished configuring *GRUB*. We can now **exit** to our Pen Drive ( *our boot media* ).

```bash

exit

```

Then unmount all of the other drives.

```bash

unmount -a

```

#### Reboot

```bash

reboot

```

---

>[!note]
>At this point, we can now **remove** the *boot media* and it should boot up into Arch.

#### Check For Internet Connection

Again we can do this by running the command:

```bash

ping www.google.com

```

---

## [Arch Linux Post Install Guide](https://www.youtube.com/watch?v=YPrhIfm3VJs)

He will show you some crucial things such as **security**, **system admin** things and **more**.

---

### Installing KDE Plasma ( Desktop Environment )

```bash

sudo pacman -S plasma sddm

```

If `Enter a selection (default=all):` appears then just continue by pressing `Enter`.

#### Installing Some Stuff

##### Terminal Emulator + Firefox

```bash

sudo pacman -S alacritty kitty firfox

```

#### Start Linux Desktop

>I am getting impatient now, hence I will only be writing the commands.

```bash

sudo systemctl enable --now sddm

```

>[!success]
>It should be all working fine.

---