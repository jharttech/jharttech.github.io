---
title: How To Prepare Your Old Computer's Hard Drive For Disposal
date: 2023-11-11
categories: [Hard Drive, Data Wipe, Disposal]
tags: [hard drive, data wipe]
toc: false
comments: false
---
[Disclaimer]({% link _tabs/disclaimer.md %})
<h1>{{ page.title }}</h1>
<h2>This tutorial can be helpful for making sure your data does not fall into someone else's hands when disposing of old hard drives or computers.</h2>
<p>In today's throwaway world, most of us have faced the issue of buying a new computer and getting rid of the old one. These old computers are ripe for the picking for those who know how to recover information from the old computer's hard drive. Most users do not even think or realize the amount of personal data that their old hard drive may contain. This tutorial will show you how to overwrite the data on your old hard drive with a series of random characters in no particular order. This will make it very difficult (NOT IMPOSSIBLE) to recover the data from the hard drive using basic tools.</p>
<p>I must mention that the process used in this article is only a small, first line of defense against data theft when disposing of an old computer. There are more advanced steps that may need to be taken by a professional depending on your specific needs, but this will get most average users started on keeping their old data out of the wrong hands.</p>
<blockquote class="prompt-warning">BE SURE YOU HAVE ALL IMPORTANT DATA FROM YOUR OLD HARD DRIVE BACKED UP TO A DIFFERENT DRIVE OR YOU MAY LOSE THE DATA PERMANENTLY!!!</blockquote>

---

<h3>Prerequisites</h3>
<li>Etcher to create live USB: <a href="https://etcher.balena.io/#download-etcher">Etcher</a></li>
<li>ISO image of a linux distribution called TinyCore: <a href="http://tinycorelinux.net/downloads.html">TinyCore</a></li>
<li>USB flash drive of 1Gb or larger. <ul><blockquote class="prompt-info">This process will erase the contents on the flash drive.</blockquote></ul></li>

---

<h3>How To</h3>
<ol>
    <li>Start by downloading the Etcher program for your Operating System using the link above. <ul><blockquote class="prompt-info">Follow the steps provided by Balena to install the Etcher program. If you prefer a different live USB creator, such as unetbootin, feel free to use it in place of Etcher.</blockquote></ul></li>
    <li>Download an ISO of TinyCore linux distribution from the link above.  Remember the location of where you save the downlaoded ISO.</li>
    <li>Insert your USB flash drive into your Computer.  Start the Etcher Program</li>
    <li>Once the Etcher program is started, use the "select from file" option to select the TinyCore-current.iso from the location you downloaded the ISO in step 2. Next, select the "Select target" and choose your USB flash drive.  Last, select "Flash!".  This will create a live USB which can be used to boot into TinyCore linux.</li>
    <li>After the Etcher program has created your new live USB, insert the USB into the machine in which you want to erase ALL data.</li>
    <li>Power on the machine and immediately repeatedly press the boot option key.<ul><blockquote class="prompt-info">This key is different based on the manufacturer of the computer.  You may need to research which key you need to press for the boot menu.<br><br>
    Also, you may need to research the proper BIOS settings for the computer in order to boot into a live USB.</blockquote></ul>
    </li>
    <li>When the boot options for TinyCore appear, select the "default" option.  TinyCore Live Operating System should now boot up.</li>
    <li>Once TinyCore has started, click on the "Mount Tool" button on the tool bar.  This will start a program that will tell you the drive label of your hard drive.  One label will be in gree.  This is the label of the live USB that you are currently booted into.<ul><blockquote class="prompt-tip">Usually this will be labeled as "sdb" or "sdb1".</blockquote></ul>
    </li>
    <li>In red you should see "sda","sda1", and so forth (Or something similar). The "sda" is the drive label and "sda1" represents a partition on the "sda" drive. The key is to find the drive that is listed in red as well as all of it's partitions. <b>MAKE NOTE OF THIS LABEL FOR LATER.</b><br>You can ignore any "sr0" and any subsets of "srX"</li>
    <li>Next, click on the "Terminal" button on the dock. This will open a Unix terminal where we will run our next command to overwrite the data on the old hard drive.</li>
    <li>Type the following command into the terminal.<ul><blockquote class="prompt-tip">Replace "sdX" where X is the label letter of your drive that you took note of in step 9 of this tutorial. In our example we would replace "sdX" with "sda"</blockquote></ul><pre><code>$ sudo dd if=/dev/urandom of=/dev/sdX bs=1M</code></pre>
    </li>
    <li>It may appear that the terminal stops responding. However, if no command error appears and the cursor is not flashing, then the command was issued successfully. Depending on your hard drive size, this process may take several hours. Once the terminal gives you an outpu of something like the following:<br><br>
    <pre><code>$ 111108189+0 records in
$ 111108189+0 records out
$ 56887392768 bytes (57GB) copied, 85620, 7 seconds, 667kb/s</code></pre><br>
    Then the process is complete and you can shut down the machine. Now your old computer is ready to be disposed of.</li>
</ol>
