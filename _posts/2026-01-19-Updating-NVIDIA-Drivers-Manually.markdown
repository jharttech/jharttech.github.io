---
title: How to Manually Update NVIDIA Drivers on Kubuntu 24
date: 2026-01-19
categories: [Linux, Notes]
tags: [linux, notes, kubuntu]
toc: false
comments: false
---
[Disclaimer]({% link _tabs/disclaimer.md %})
<h2>This is a small note for myself or anyone else who finds they need to update their Kubuntu 24.04 system's NVIDIA driver manually instead of using the one provided in "ubuntu-drivers" or "apt".</h2>
<p>First, go find the Nvidia Driver that you want to install.  The download will be a "DRIVER_VERSION".run file.</p>
<p>Next, make the .run file executable so that we can run the file.</p>
<blockquote class="prompt-tip"><pre><code>$ chmod +x /home/$USER/path/to/"DRIVER_VERSION".run</code></pre></blockquote>
<p>Now stop the display manager so we can cleanly install the driver. To do this use one of the TTY terminals by pressing "CTRL + ALT + F2 thru F6". In the TTY Terminal log in and run:</p>
<blockquote class="prompt-tip"><pre><code>$ sudo systemctl stop sddm.service</code></pre></blockquote>
<p>Once the display manager is stopped run the driver installer.</p>
<blockquote class="prompt-tip">NOTE: The installation has many options or variables so I am not going to go into details and leave that up to each install.</blockquote>
<blockquote class="prompt-tip"><pre><code>$ sudo /home/$USER/path/to/"DRIVER_VERSION".run</code></pre></blockquote>
<p>Follow the on screen prompt to install the driver with the options desired.  Once the installer has finished restart the machine:</p>
<blockquote class="prompt-tip"><pre><code>$ reboot</code></pre></blockquote>
<p>When the machine boots back up, run the following command to see if the driver version you wanted is being shown:</p>
<blockquote class="prompt-tip"><pre><code>$ nvidia-smi</code></pre></blockquote>
<p>The last thing I like to do is disable the apt package version of the driver so that updating my system does not break the driver version I have installed.  To do this you tell apt to mark the package
and modules as manual:</p>
<blockquote class="prompt-tip">NOTE: The command below is using the nvidia-driver-570-open package and modules to be set to manual</blockquote>
<blockquote class="prompt-tip"><pre><code>$ sudo apt-mark manual "nvidia-driver-570-open"</code></pre></blockquote>
<blockquote class="prompt-tip"><pre><code>$ sudo apt-mark manual "linux-modules-nvidia-driver-570-open-generic"</code></pre></blockquote>
<p>I also like to set the nvidia-prime tool to manual as I had issues with this breaking things in the past.</p>
<blockquote class="prompt-tip"><pre><code>$ sudo apt-mark manual "nvidia-prime"</code></pre></blockquote>
<blockquote class="prompt-tip">NOTE: As always, I take no responsibility of any changes you make to your system and I point you to the disclaimer link to the top of this page!!!</blockquote>