#Although I used this fix for Arch Linux This also works for Nobara as well when having issues with steam choosing the wrong vulkan driver.

I made a post in the Arch Linux newbie corner here https://bbs.archlinux.org/viewtopic.php?pid=2040091#p2040091
and Seth was kind enough to walk me though this process.
Together we found out that why none of my Steam runtime games were launching looking at the logs I posted at the main hub repo. which will be posted in
in the logs directory at one point.

Fyi having ibt=off is a must to get any games working with on a Arch Linux pc that has an intel cpu and a Nvidia card
https://github.com/NVIDIA/open-gpu-kernel-modules/issues/256 also apparently open suse has some issues too so keep that in mind

Also I did some other work trying to make sure I had all the right Nvidia drivers and I had to do some work with making sure xorg was working right
using the guide here https://wiki.archlinux.org/title/Xorg#General and I didn't have nvidia-settings package installed so I made sure to grab that

Apparently Steam Runtime chooses at random which proton Vulkan Driver to use. so if its using the wrong one you don't have installed it fails to launch 
Or maybe it just has trouble detecting which vulkan driver you actually have installed.
A simple fix would be to have an option in the Steam play settings which graphics drivers you want Vulkan to use. Although not sure they'll actually do that

So you have to blacklist all the other drivers in the /usr/share/vulkan directory here's how you get that directory and rename them.
I also have a terminal output that I saved so you can find it later


https://github.com/Jedhless-Huudie/Debugging-Linux-Records/blob/HUB/terminal-output/Blacklist%20Non%20nvidia%20vulkan%20drivers

Here is what I did to blacklist all other drivers except Nvidia. Steps to do this is also described here https://github.com/ValveSoftware/steam-runtime/issues/312

$cd ..

$cd ..

$ cd usr

$ cd share

$ cd vulkan

$ cd icd.d

$ sudo mv amd_icd32.json amd_icd32.json.disabled

$ sudo mv amd_icd64.json amd_icd64.json.disabled

$ cd .. 

$ cd implicit_layer.d

$ sudo mv amd_icd32.json amd_icd32.json.disabled

$ sudo mv amd_icd64.json amd_icd64.json.disabled



After that my games started working.
I'll post in Steam runtime issues if I have anything else to report.
