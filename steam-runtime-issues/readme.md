DEBUGGING 101
Locate wherever your proton version is saved. find user_settings.py or sample_user_settings.py.
Rename to user_settings.py if needed.
Make sure that inside of the file the # is removed in front of 
"WINEDEBUG": "+timestamp,+pid,+seh,+unwind,+debugstr,+loaddll,+mscoree", 
This should give you the proton logs in the home directory.
PROTON_LOG=1 %command% log in the game launch options is supposed to do this
But it doesn't always work for me. Hope this helps
