## Logrotate

```
/var/log/autoheal.log {
        size 1M             
        rotate 3
        delaycompress
        compress
        notifempty
        missingok
        copy
}
```

**size 1M :** With this, the log file is rotated when the specified size is reached. Size may be specified in bytes (default), kilobytes (sizek), or megabytes (sizem).

**rotate 3 :** Once a log file is rotated, we can specify what should happen to them through a different set of directives. For example, we could send the rotated files to an email or simply discard them. We could limit the number of rotated files we keep in our system through the rotate n directive where n is an integer value. Once the limit n is reached, any further rotation will remove the oldest rotated log file such that the limit is adhered to. For example, to keep only 3 rotated /var/log/nginx/access.log files:
**delaycompress :** If compression is on, delay compression until the next rotation. This allows at least one rotated but uncompressed file to be present. Useful if you want yesterday’s logs to stay uncompressed for troubleshooting. It is also helpful if some program might still write to the old file until it is restarted/reloaded, like Apache.
**compress:** Compression is on. Use nocompress to turn it off.
**notifempty :** Don’t rotate if the log file is empty.
**missingok :** It’s okay if the log file is missing. Don’t Panic.
**copy :** 

Links https://www.baeldung.com/linux/rotating-logs-logrotate
      https://opensource.com/article/21/10/linux-logrotate
      https://www.techrepublic.com/article/manage-linux-log-files-with-logrotate/
      
