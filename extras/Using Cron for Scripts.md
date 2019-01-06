# Using Cron for Scripts

You can schedule tasks using cron jobs. You can also include scripts within your cron jobs.

# Video



## Code

```

# min hour day_of_month month day_of_week

0 14 * * * /home/scripts/pingips > /home/scripts/results.txt

```


## Output

```

# cat /home/scripts/results.txt
192.168.101.240 is reachable
200.200.200.200 is not reachable
192.168.101.250 is reachable



```

## Summary

All in all, cron jobs can make things easier to automate. You can even pipe scripts to email your results as well. Example: ``` 0 14 * * * /home/scripts/pingips | mail -s "results for pings" dennis@mail.com ```
