btw Please check out https://github.com/Jedhless-Huudie/Debugging-Linux-Records/blob/HUB/steam-runtime-issues/Enabling-only-nvidia.md
It has more info on why you need to manually disable all the vulkan drivers that won't work with your system.

This was caused by a system Update aka
Sudo pacman -Syu

It updated the kernel and re-created amd_icd32.json and amd_icd64.json.
interestingly enough the amd_icd32.json.disabled and amd_icd64.json.disabled were still there.
so I had 4 amd_icd's in /usr/share/vulkan/icd.d/ and /usr/share/vulkan/implicit_layer.d/

Ok I am Copying an pasting what you need to do to fix this. 
(This is a process of Disabling Incompatible Vulkan drivers. 
Its is listed Enabling-only-nvidia but I am posting this here)

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

Instead of having two more .disabled files 
since mv moves the file in the folder using the .disabled
it replaced the old .disabled files in the /usr/share/vulkan/icd.d/ and /usr/share/vulkan/implicit_layer.d/

Nice to know that in future -sudo pacman -Syu might create more Amd mesa drivers.

for more details

Btw if you have another graphics card with a different driver disable the ones you don't need by adding a .disabled to the file
Espicially if you get this error, 
