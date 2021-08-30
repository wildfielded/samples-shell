# Shell scripting examples for references
1. Mail traffic counter    
[**`/sh-freebsd/mailstat/mailstat`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/mailstat/mailstat)    
Standard sendmail's log processed with grep, sed, mreport (now moved from ports),
then generate HTML file with statistics (per-user, in/out total, in/out local,
in/out with headquarter).    
----
2. Proc Checkers    
[**`/sh-freebsd/check/checkbge`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/check/checkbge) - One server had a very buggy NIC **`bge`**    
[**`/sh-freebsd/check/checkkas`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/check/checkkas) - Sometimes the Kaspersky Anti-Spam needs to be kicked    
[**`/sh-freebsd/check/checkklms`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/check/checkklms) - And sometimes the Kaspersky Anti-Virus needs to be kicked too    
----
3. Cisco configuration files rotation    
[**`/sh-freebsd/configrotate/confrot`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/configrotate/confrot) - Script    
[**`/sh-freebsd/configrotate/confrot.conf`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/configrotate/confrot.conf) - It's config    

Strange requirements were as follows:    
- The script is launched daily by cron after the end of work to save the changes made by the network admins for the day (They dump configs to a TFTP-server).
- The number of files and their paths can change, i.e. keeping filelist in a separate file (with comments support) is more convenient.
- If there were no changes, nothing happens.
- If only a line starting with "`!`" or "`:`" "`ntp clock-period`" is changed in the **configfile**, then this is not considered a new version.
- Else, current **configfile** is copied to **`configfile.00`**, **`\*.00`** is moved to **`\*.01`**, and so on.
- The number of configfile versions must be at least 10. Trailing versions (**`\*.11`** and furthermore) should only be removed if they are older than 92 days (3 months).
- We need some logging.
----
4. Files synchronizing    
[**`/sh-freebsd/syncfiles/syncf`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/syncfiles/syncf) - Makes files the same on different servers    
- Uses **rsync** (that is, it syncs new files only).
- Format: **`syncf /path/to/dir/file`** (for specific file) or **`syncf /path/to/dir`** (full directory).
----
