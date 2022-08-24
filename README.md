# Legendary-OrangePi-i96
Image that fixes the USB port on the Orange Pi i96 to use High Speed (480M) instead of Full Speed.<br>
<br>
These also contained upgraded OS versions.  Debian Bullseye (11) is available.<br>
<br>
<strong>You do not have to build this yourself.</strong>  Images are available <a href="https://github.com/TheRemote/Legendary-OrangePi-i96/releases">here in the releases section</a>.<br>
<br>
<h2>Fixes</h2>
<ol>
  <li>Fixed USB port to allow "High Speed" USB devices instead of locking them to "Full Speed"</li>
  <li>Fixed buggy UART not resetting properly which often breaks copying/pasting through a serial terminal</li>
  <li>Fixed sound issues that would prevent rebooting the system successfully after first startup</li>
</ol>
<h2>Build Instructions</h2>
You should first clone the OrangePi_Build repository:<br>
<pre>git clone https://github.com/orangepi-xunlong/OrangePi_Build.git
cd OrangePi_Build
./Build_OrangePi.sh</pre><br>
Choose the "Orange Pi I96" option which will create the "OrangePiRDA" folder.<br>
<br>
The files in this repository are meant to replace the stock OrangePiRDA ones that are generated (specifically in the scripts folder).  You simply copy them over the top of your generated folder like this:<br>
<pre>cd ..
git clone https://github.com/TheRemote/Legendary-OrangePi-i96.git
cp -R Legendary-OrangePi-i96/OrangePiRDA/* OrangePiRDA/</pre>
You may now build the image the same way I did!<br>
Ubuntu is not building correctly yet.<br>
<br>
<h2>Version History</h2>
<ol>
  <li>August 24th 2022 - V1.1 - Added sound fix and UART fix from official OrangePi repository pull requests</li>
  <li>August 23rd 2022 - V1.0 - Initial Release</li>
</ol>
<h2>Credits</h2>
The drama surrounding this board is ridiculous.  Is it a great board?  Not really.  It also costs like $7 on Amazon.  Is it a good board for $7?  Yes it is, especially in 2022 when Pis are routinely over $100.<br><br>
This board honestly isn't more broken than any other boards were at release.  It just never got support and it was almost right from the start.  It never received support from Armbian and Orange Pi has never supported it either.<br><br>
What hope is there then?  The community basically.  This image is just a compilation of fixes from people who dreamed of something better for the board and submitted PRs or fixes around the internet.<br><br>
This image is simply putting all of the community's work together and updating the OS to a newer version so we can pretend Orange Pi / Armbian wanted to support it.  You'll have to judge for yourself if it's enough.<br><br>
<br>
<a href="https://forum.armbian.com/topic/3232-orange-pi-2g-iot/page/6/">Credit to Gabor Hidvegi for the patch itself</a> as I found his patch (which wasn't as effective for the 2G version as he would have liked due to the modem initialization dropping the speed) but for the regular i96 this patch is working as-is.<br>
<a href="https://github.com/orangepi-xunlong/OrangePiRDA_kernel/pull/2">Credit to GMMan</a> for the pull request on the official repository to fix sound playback kernel parameter issues<br>
<a href="https://github.com/orangepi-xunlong/OrangePiRDA_kernel/pull/3">Credit to GMMan again</a> for the pull request on the official repository to fix UART serial issues fixing copy/pasting<br>