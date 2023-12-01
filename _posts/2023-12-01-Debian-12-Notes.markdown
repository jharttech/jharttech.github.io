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
<p>Most of the programs mentioned above set in "/usr/sbin". If you type the following command into the terminal you will see "/usr/sbin" is not currently in the PATH.</p>
<blockquote class="prompt-tip"><pre><code>$ echo $PATH</code></pre></blockquote>
<p>In order to use them without needing the FQP we will add that path and directory to the PATH. To do this we will run the following command in the terminal:</p>
<blockquote class="prompt-tip"><pre><code>$ export PATH=$PATH:/usr/sbin</code></pre></blockquote>
<p>Now if we run the echo $PATH command above, we should now see /usr/sbin in the PATH.</p>