DEBUGGING 101 
If your trying to get Proton_log launch options aren't working.
change sample_user_settings.py to user_settings.py
Make sure the # is removed in front of 
"WINEDEBUG": "+timestamp,+pid,+seh,+unwind,+debugstr,+loaddll,+mscoree", 
This should give you the proton logs in the home directory.
PROTON_LOG=1 %command% log is supposed to do this in the launch options
But it doesn't always work for me. Hope this helps