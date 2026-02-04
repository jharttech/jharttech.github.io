---
title: How to install and run VSCode on a ChromeOS environment with the Linux Development Environment turned on
date: 2026-02-04
categories: [Linux, ChromeOS, Notes, VSCode]
tags: [linux, notes, ChromeOS, VSCode]
toc: false
comments: false
---
[Disclaimer]({% link _tabs/disclaimer.md %})
<h2>Script for simplifying the installation of vscode using linux development environement on ChromeOS</h2>

# Notes
This bash script is designed with a special use case.  This script is designed to help students quickly setup a vscode environment on an HP 14 G7 Chromebook for use at a Skills USA Compitition.
If the chromebook is set to ephemeral mode, a reboot will wipe the linux vm.  

# Setup
The following are the steps to get vscode on a ChromeOS environment that has Linux Development Environment enabled.

1. Go to ChromeOS settings, search for linux, then under the Linux Development Environment click the "Setup" button.  Follow the onscreen setup.
2. Use the ChromeOS app drawer to search for "Terminal" and launch it.  Click on "penquin" to launch your linux terminal.
3. Once linux has been configured and installed, type the following command in the terminal and press enter to download the install script:
    <blockquote class="prompt-tip"><pre><code>$ wget https://raw.githubusercontent.com/jharttech/vscode_on_chromeOS/main/install.sh</code></pre></blockquote>
4. Now the install.sh script should be downloaded onto the linux vm users home directory.
5. Type the following command in the terminal and press enter to make sure the install.sh file exists in your linux home directory.  If it does not exist then something in the steps above has gone wrong.
    <blockquote class="prompt-tip"><pre><code>$ ls</code></pre></blockquote>
6. Now make the install.sh file executable by typing the following command and pressing enter:
    <blockquote class="prompt-tip"><pre><code>$ chmod +x install.sh</code></pre></blockquote>
7. Run the install script by typing the command below and pressing enter:
    <blockquote class="prompt-tip"><pre><code>$ ./install.sh</code></pre></blockquote>
8. If the install script completed without issue then vscode should now be listed in the ChromeOS app drawer under the linux apps area. If the icon is a generic icon, reboot your chromebook to refresh
icon cache of the chromeOS.

Feel free to adjust the install script to meet your own needs.
