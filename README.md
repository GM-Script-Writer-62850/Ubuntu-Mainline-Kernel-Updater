<!--
   I suggest reading this on the webpage at github:
   https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater#readme
-->
About:<blockquote>
This Updater was made to alert the user of update for mainline kernels and to make installing them noob/newbie friendly.<br>
You can manually install the kernels from <a target="_blank" href="http://kernel.ubuntu.com/~kernel-ppa/mainline/?C=N;O=D">here</a> without using this script.<br>
<br>
If you think this looks long and complicated, It is just because I have there are 5 different ways you can download this project based on your personal preferences. If you want a recommendation just use eigther <i>Terminal Install</i> or <i>Recovery Console</i></blockquote>
<hr>
GUI Install:<blockquote>
Download the zip archive (there is a button near the top of the page) and extract it<br>
Drag and drop the install file into a terminal window and press enter<br>
If that does not work type "bash " then repeat the above step<br>
It will look like <code>bash '/path/to/install'</code><br>
Type your login password when prompted
</blockquote>
<hr>
Terminal Install:<br>
<blockquote>
Step 1: cd to /tmp<br>
<pre><code>cd /tmp</code></pre>

Step 2: Download (Method 1/5: Use <code>git</code>)
<pre><code>git clone git://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater</code></pre>

Step 2: Download (Method 2/5: Use <code>wget</code> to download a zip archive and extract it)
<pre><code>wget https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip -O Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip</code></pre>

Step 2: Download (Method 3/5: Use <code>curl</code> to download a zip archive and extract it)
<pre><code>curl https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip > Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip</code></pre>

Step 2: Download (Method 4/5: Use <code>wget</code> to download a tar.gz archive and extract it)
<pre><code>wget https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.tar.gz -O Ubuntu-Mainline-Kernel-Updater.zip
tar -zxvf Ubuntu-Mainline-Kernel-Updater-master.tar.gz</code></pre>

Step 2: Download (Method 5/5: Use <code>curl</code> to download a tar.gz archive and extract it)
<pre><code>curl https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.tar.gz > Ubuntu-Mainline-Kernel-Updater.zip
tar -zxvf Ubuntu-Mainline-Kernel-Updater-master.tar.gz</code></pre>

Step 3: Run the <code>install</code> script (If you used <code>git</code> for <i>Step 2</i>)
<pre><code>bash Ubuntu-Mainline-Kernel-Updater/install</code></pre>

Step 3: Run the <code>install</code> script (If you did <b>NOT</b> use <code>git</code> for <i>Step 2</i>)
<pre><code>bash Ubuntu-Mainline-Kernel-Updater-master/install</code></pre>

Step 4: Check for kernel update (If you would like a release canidate kerenl remove <code>-no-rc</code> from this command)
<pre><code>KernelUpdateChecker -no-rc</code></pre>
</blockquote>
<hr>
Recovery Console: (Also works if you are too lazy to do the above)<blockquote>
<pre><code>curl http://pastebin.com/raw.php?i=hHS6rf6w | tr -d '\r' > /tmp/script
sh /tmp/script</code></pre>
Alternative:
<pre><code>wget http://pastebin.com/raw.php?i=hHS6rf6w -O /tmp/script.bug
tr -d $'\r' &lt; script.bug &gt; script
sh /tmp/script</code></pre>
You can view the <a target="_blank" href="http://pastebin.com/hHS6rf6w">source code</a> of that script if you like.<br>
</blockquote>
<hr>
Advanced usage examples and notes:<blockquote>
<code>KernelUpdateChecker -k -r quantal -no-rc -v 3.5</code><br>
This would force the script to generate a install script for the latest 3.5 kernel compiled for quantal that is not a release candidate even if you are running a newer kernel<br>
<code>-k</code> forces the script to make a installer regardless of now new the current running kernel is<br>
<code>-r quantal</code> tells the script to use quantal kernels even if you are using raring (13.04) or precise (12.04)<br>
<code>-no-rc</code> tells the script to ignore release candidate kernels<br>
<code>-v 3.5</code> tells the script you only want a kernel with a version number starting with 3.5, you can use the entire kernel version number to force a exact version<br>
<code>/tmp/kernel-update --silent</code> will install the kernel without asking questions<br>
<code>/tmp/kernel-update --uninstall</code> will purge the kernel it would normally install from the system<br>
If there is no update <code>/tmp/kernel-update</code> will exit without doing anything, keep in mind that <code>/tmp/kernel-update</code> does not exist until a little over 60 seconds after login<br>
If the new kernel is detected as not installed it will exit with status 1, will exit normally if it did not try to install it
</blockquote>
