# Install

### Step 1. Best of both worlds -- dual boot

Chances are your PC comes installed with some version of Windows. While Windows is good for major everyday tasks, scientific computing doesn't usually happen on Windows for reasons already explained in the intro page. However, you will still need Windows to write your papers  in MS Word, create your supplementary data Excel files, and develop your publication figures in Adobe Illustrator. The solution is then to install Linux besides Windows, and make your PC dual boot. You will then have the option of booting into Linux or Windows on starting up your PC.

Generally, the two steps involved in making your PC dual boot are:

1. Partitioning your hard disk to have unallocated space in to which Linux will be installed.
2. Installing your Linux into this unallocated space.

A handy guide to partition the hard disk space from within Windows 10 for Linux installation can be found at [http://dailylinuxuser.com/2015/11/how-to-shrink-windows-10-to-make-space.html](http://dailylinuxuser.com/2015/11/how-to-shrink-windows-10-to-make-space.html)

### Step 2. Selecting a Linux distribution.

There are many different Linux distributions \(or distros as pundits call them\) often each with multiple flavors. For example, one popular distro is Ubuntu, that has different flavors such as:

* Kubuntu — Ubuntu with the K Desktop environment.
* Lubuntu — Ubuntu that uses LXDE.
* Mythbuntu — Designed for creating a home theatre PC with MythTV.
* Ubuntu Budgie — Simplicity and elegance – Budgie desktop powered by Ubuntu.
* Ubuntu GNOME — Ubuntu with the GNOME desktop environment.

There are different reasons to select different distributions, and flavors therein. One reason might be hardware compatibility -- you have an old PC and Ubuntu's latest LTS \(long term support\) release might require more powerful hardware unavailable on your PC. Time to shift gears and choose a lightweight Ubuntu flavor such as Lubuntu. Also different major distributions have different package management and customization features. You can select one you like the most. No matter the situation, there is always a Linux distribution that will play by your rules. Fun fact: The popular Linux distribution Kali Linux is dedicated to computer hackers for developing malwares and delving in cyber-crime!

At the time of this article being originally written, Elementary OS is popular in the lab. Looks like Mac OS, and has all the power and technical semblance of Ubuntu -- same package managers, same app support, wide availability of drivers etc.

### Step 3. Installing the Linux distribution

The exact steps are dependent on the Linux distro you have selected but generally involves the following.

1. Dowloading the distro ISO file from website. For example, you can download the latest Elementary OS ISO file for free \(just put in $0 in the price box\) from [https://elementary.io/](https://elementary.io/)
2. Burning the ISO file onto a USB memory stick and making it bootable. For example, you can use a program like Unetbootin available at [https://unetbootin.github.io/](https://unetbootin.github.io/)
3. Docking the USB memory stick in to your USB port and \(re\)starting the system. If your burning was successful, you will be able to boot in to the OS setup screen. Just follow on-screen directions.
4. **Be careful when setting up disk space allocation.** Generally, all you need to specify are the **root** and **swap** disk space. Ideally, for your swap you will allocate the same amount of disk space as your available RAM and put rest of the substantial allocation from **Step 1** \(say 1 terabyte\) for your root. The root will hold all your files and home directory, so make sure you have enough space there. For swap, if you allocate more memory than your RAM, it will be wasteful -- the swap space on the disk is where your entire RAM content is dumped if your OS knows it is about to crash or if you hibernate your system as opposed to shutting it down.

For detailed instructions on installing the latest Elementary OS, follow the instruction on this page: [https://itsfoss.com/guide-install-elementary-os-luna/](https://itsfoss.com/guide-install-elementary-os-luna/)

