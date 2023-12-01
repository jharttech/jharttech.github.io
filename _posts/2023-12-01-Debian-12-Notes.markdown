---
title: Debian 12 Notes for Adding Included Commands to the Path Environment
date: 2023-12-01
categories: [Linux, Notes]
tags: [linux, notes, debian]
toc: false
comments: false
---
[Disclaimer]({% link _tabs/disclaimer.md %})
<h2>This is a small note for myself or anyone else who finds they need a command in Debian 12, but get a "no command found" error.</h2>
<p>In order to use commands like usermod, shutdown, reboot, and many others, we need to add the directory that stores these programs to the PATH Environment. Debian 12 leaves this directory out of the PATH by defaut.</p>
<p>Most of the programs mentioned above set in "/usr/sbin". If you type the following command into the terminal you will see <b>/usr/sbin</b> is not currently in the PATH.</p>
<blockquote class="prompt-tip"><pre><code>$ echo $PATH</code></pre></blockquote>
<p>In order to use them without needing the FQP we will add that path and directory to the PATH. To do this we will run the following command in the terminal:</p>
<blockquote class="prompt-tip"><pre><code>$ export PATH=$PATH:/usr/sbin</code></pre></blockquote>
<p>Now if we run the <b>echo $PATH</b> command above, we should now see /usr/sbin in the PATH.</p>
<blockquote class="prompt-tip">Note: This will only last for the current shell session.  If you want to make the change permanent please continue below.</blockquote>
<p>To make the change to the PATH permanent we need to make a change to the <b>~/.bashrc</b> file (or .zshrc if using zsh).  To make this change we will use "vim" (you can use nano or other terminal editors) to open the <b>~/.bashrc</b> file:
<blockquote class="prompt-tip"><pre><code>$ vim ~/.bashrc</code></pre></blockquote>
<p>Next we will add a line to the bottom of the open <b>~/.bashrc</b>:
<blockquote class="prompt-tip"><pre><code>$ ...
$ #Adding /usr/sbin to this users path
$ export PATH=$PATH:/usr/sbin</code></pre></blockquote>
<p>Save and close the file.  We now need to make sure our shell is aware of the change.  To do that we run the following command:</p>
<blockquote class="prompt-tip"><pre><code>$ source ~/.bashrc</code></pre></blockquote>
<p>That's it.  You should now have the <b>/usr/sbin</b> directory in your path across each shell session.</p>