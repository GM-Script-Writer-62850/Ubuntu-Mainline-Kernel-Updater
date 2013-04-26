To install drag and drop the install file into a terminal window and press enter<br>
if that does not work type "bash " then drop repeat the above step<br>
Quick install terminal commands:<br>
<pre><code>cd /tmp
git clone git://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater
bash Ubuntu-Mainline-Kernel-Updater/install
KernelUpdateChecker -no-rc</code></pre>

If you dont want to use the git command:
<pre><code>cd /tmp
wget https://github.com/GM-Script-Writer-62850/Ubuntu-Mainline-Kernel-Updater/archive/master.zip -O Ubuntu-Mainline-Kernel-Updater.zip
unzip Ubuntu-Mainline-Kernel-Updater.zip
bash Ubuntu-Mainline-Kernel-Updater-master/install
KernelUpdateChecker -no-rc</code></pre>
