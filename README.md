This Updater was made to alert the user of update for mainline kernels and to make installing them noob/newbie friendly.<br>
You can manually install the kernels from <a target="_blank" href="http://kernel.ubuntu.com/~kernel-ppa/mainline/?C=N;O=D">here</a> without using this script.<br>
<br>
If you think this looks long and complicated, It is just because I have 6 different install procedures listed here for you to pick from based on your personal preferences, if you want a recommendation just use one of the multi line code blocks<br>
<br>
GUI Install:<br>
&nbsp;&nbsp;Download the zip archive (there is a button near the top of the page) and extract it<br>
&nbsp;&nbsp;Drag and drop the install file into a terminal window and press enter<br>
&nbsp;&nbsp;If that does not work type "bash " then repeat the above step<br>
&nbsp;&nbsp;It will look like <code>bash '/path/to/install'</code><br>
&nbsp;&nbsp;Type your login password when prompted<br>
Terminal Install:<br>
<pre><code>cd /tmp
git clone git://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater
bash Ubuntu-Mainline-Kernel-Updater/install
KernelUpdateChecker -no-rc</code></pre>

If you don't want to use the git command:
<pre><code>cd /tmp
wget https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip -O Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip
bash Ubuntu-Mainline-Kernel-Updater-master/install
KernelUpdateChecker -no-rc</code></pre>

If you don't want to use wget command:
<pre><code>cd /tmp
curl https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip > Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip
bash Ubuntu-Mainline-Kernel-Updater-master/install
KernelUpdateChecker -no-rc</code></pre>

If you are in a Recovery Console:
<pre><code>curl http://pastebin.com/raw.php?i=5UBBzzky | tr -d '\r' > /tmp/script
sh /tmp/script</code></pre>
<pre><code>wget http://pastebin.com/raw.php?i=5UBBzzky -O /tmp/script.bug
tr -d $'\r' < script.bug > script
sh /tmp/script</code></pre>
Alternative:
You can view the <a target="_blank" href="http://pastebin.com/5UBBzzky">source code</a> of that script if you like.

If you don't want to use curl you can view the source code of every file and save it then install the script

Advanced usage examples and notes:<br>
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
