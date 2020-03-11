Dromedary Studio
================

OS X Install Guide
------------------

This guide will take you through the steps to install and run Dromedary Studio on
OS X. We will be using a program called Wine. Wine is compatibility layer for Linux and
macOS which enables Windows applications to be run seamlessly.

Automatic installation
======================

Not available yet, please follow the steps under *Manual installation* in the meantime.

Manual installation
===================

Step 1: Installing Homebrew
---------------------------

Homebrew is the easiest way to install Wine on Mac. Follow these steps:

#. Open your prefered terminal application. OS X comes with ``Terminal.app`` installed by
   default.

#. Homebrew requires ``Command Line Tools (CLT) for Xcode``. You might already have
   this installed. This will take some time to download and install depending on 
   your internet speed, so be patient. Install it with:

   ::

        xcode-select --install

#. Copy and paste the following line into your terminal, and hit ``ENTER``.
   
   ::

        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

#. Once Homebrew is installed, close ``Terminal`` and relaunch it. Homebrew will tell you
   to run ``brew doctor``. Do this now. This will check for issues with your
   installation and suggest fixes.

   ::
        
        brew doctor

#. Homebrew might tell you to that you need to accept the license for ``Xcode``. Do
   so with this command.

   ::
        
        sudo xcodebuild -license

#. Run ``brew doctor`` one final time to verify that Homebrew is ready.

   ::

        brew doctor

   You should now see ``system is ready to brew``.

Step 2: Installing Wine with Homebrew
-------------------------------------

#. Update Homebrew's formula (list of packages).

   ::

        brew update

#. Install ``XQuartz/X11`` dependency. You will be prompted to provide your user account
   password.

   ::

        brew cask install xquartz

#. You are now ready to install Wine.

   ::

        brew cask install wine-stable

Step 3: Install Dromedary Studio
--------------------------------

Hang in there we are almost done.

#. ``mono`` is a open source implementation of Microsoft's .NET Framework. Install it
   now.

   ::

        brew install mono

#. Download ``setup.exe`` installer for Dromedary from the course Google Drive. Let's
   suppose you downloaded it to the default downloads folder for your user account
   ie, : ``~/Downloads/setup.exe``.

#. Launch ``terminal`` and navigate to your downloads folder.

   ::

        cd ~/Downloads

#. Install Dromedary Studio through the Wine emulation layer.

   ::

        wine setup.exe

   The regular Windows graphical installer will pop up for Dromedary Studio. Accept the
   license agreement and install to the default location. **You will see two error messages
   just click Ok to ignore them.**

#. Locate ``pathfix.reg`` file. You will need to import into Wine's Windows registry.

   ::

        cd <location of pathfix.reg>
        wine regedit pathfix.reg

Step 4: Run Dromedary
---------------------

Open ``terminal`` and launch Dromedary Studio with the following command

::

    wine DromedaryStudio.exe

Dromedary Studio should open in a window.

Step 5: (Optional) Add dock icon
--------------------------------

Included in this directory you will find a Apple Script ``Dromedary Studio.app``.
Drag this file to your dock to simplify launching Dromedary Studio.
