GUI Install:<br>
Download the zip archive (there is a button near the top of the page) and extract it then drag and drop the install file into a terminal window and press enter<br>
If that does not work type "bash " then repeat the above drag/drop then enter steps<br>
It will look like <code>bash '/path/to/install'</code><br>
Type your login password when prompted<br>
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

If you don't want to use wget:
<pre><code>cd /tmp
curl https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip > Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip
bash Ubuntu-Mainline-Kernel-Updater-master/install
KernelUpdateChecker -no-rc</code></pre>

If you don't want to use curl you can view the source code of every file and save it then install the script

Advanced usage examples:<br>
<code>KernelUpdateChecker -k -r quantal -no-rc -v 3.5</code><br>
This would force the script to genearte a install script for the latest 3.5 kernel compiled for quantal that is not a release canidate even if you are runnin a newer kernel<br>
<code>-k</code> forces the script to make a installer regardless of the current running kernel<br>
<code>-r quantal</code> tells the script to use quantal kernels even if you are using raring (13.04) or precise (12.04)<br>
<code>-no-rc</code> tells the script to ignore release canidate kernels<br>
<code>-v 3.5</code> tells the script you only want a kernel with a version number starting with 3.5, you can use the entire kernel version number to force a exact version
