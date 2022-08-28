DEBUGGING 101 
If your trying to get Proton_log launch options aren't working.
change sample_user_settings.py to user_settings.py
Make sure the # before 
"WINEDEBUG": "+timestamp,+pid,+seh,+unwind,+debugstr,+loaddll,+mscoree", 
is removed.