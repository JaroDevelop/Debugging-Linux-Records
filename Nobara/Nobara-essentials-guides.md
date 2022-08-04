Essential Utils
https://docs.fedoraproject.org/en-US/quick-docs/dnf/  ,
https://docs.fedoraproject.org/en-US/quick-docs/switching-desktop-environments/  ,
https://old.reddit.com/r/Fedora/comments/jvjqhq/switch_from_gnome_to_kde/

Essential Forum posts
https://github.com/ValveSoftware/Proton/issues/3706#issuecomment-981630630  ,
https://steamcommunity.com/app/261550/discussions/0/2144217924392222478/
Esential Commands
 
Glorius eggroll told me to use this command to try to fix discord

sudo vim $(which discord)

discord-bin --no-sandbox --ignore-gpu-blocklist --disable-features=UseOzonePlatform 
--enable-features=VaapiVideoDecoder --use-gl=desktop --enable-gpu-rasterization --enable-zero-copy
