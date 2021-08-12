# Shell scripting examples for references    
1. Mail traffic counter    
[**`/sh-freebsd/mailstat/mailstat`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/mailstat/mailstat)    
Standard sendmail's log processed with grep, sed, mreport (now moved from ports),
then generate HTML file with statistics (per-user, in/out total, in/out local,
in/out with headquarter).    
----
2. Cisco configuration files rotation    
[**`/sh-freebsd/configrotate/confrot`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/configrotate/confrot) - Script    
[**`/sh-freebsd/configrotate/confrot.conf`**](https://github.com/wildfielded/samples-shell/blob/master/sh-freebsd/configrotate/confrot.conf) - It's config    
Strange requirements was:    
- The script is launched daily by cron after the end of work.
- The number of files and their paths can change, i.e. keeping filelist in a separate file (with comments support) is more convenient.
- If there were no changes, nothing happens.
- Else, current **configfile** is copied to **configfile.00**, **\*.00** is copied to **\*.01**, and so on.
- The number of configfile versions must be at least 10. When trailing version (**\*.11** and furthermore) is older than 92 days (3 months), it should be deleted.
----
