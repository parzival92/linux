# Schedule tasks to run at a set date and time

- Scheduling Jobs with cron

```
cat /etc/crontab
* * * * * user some_command
min  hour  day_of_month  month  day_of_week
0-59  0-23    1-30       1-12      0-6
* = match all possible value (i.e every hour)
, = match multiple values(i.e 15,45)
- = rnage of value (2-4)
/ = Specifies steps (i.e. */4)
```

- cron job will use full path of command

```
crontab -e 
35 6 * * * /usr/bin/touch test_passed
# Created file at 6:35 AM using touch
```

```
crontab -l
sudo crontab -e -u jane
crontab -r 
```

```
daily - /etc/cron.daily/
hourly = /etc/cron.hourly/
monthly = /etc/cron.monthly/
weekly = /etc/cron.weekly/
sudo cp shellscript /etc/cron.hourly/
sudo chmod +rx /etc/cron.hourly/shellscript
sudo rm /etc/cron.hourly/shellscript
```

- Scheduling Jobs with anacron

```
sudo vim /etc/anacrontab
#period in days   #delay in minutes job-identifier command
    1                   5              cron.daily   nice run-parts
    7                   25             cron.weekly  nice run-parts
    @monthly            45             cron.monthly nice run-parts
```
- anacron -T to test syntax

- Scheduling Jobs with at

```
at 15:00
at 'August 20 2022'
at '2:30 August 20 2022'
at ' now + 30 minutes'
at ' now + 30 hours'
at ' now + 30 days'
at ' now + 30 weeks'
at ' now + 30 months'
```

```
atq
at -c 20
```

## Verify completion of scheduled jobs

```
sudo cat /var/log/cron
sudo greo CMD /var/log/cron
```
- Use MAILTO in crona and anacron
```
sudo vim /etc/anacrontab/
sudo grep anacron /var/log/cron
sudo grep test_job /var/log/cron #job identifier
```
## Q&A

- What is the command to see the jobs that are scheduled to run in at utility?
Using the correct command, identify the currently scheduled jobs under user bob and save the command output in /home/bob/at_jobs.txt file.
```
atq > /home/bob/at_jobs.txt
```

- Remove all at jobs that exist for the user bob.
```
atq
at -r 1
```
- Add this command to the crontab of root:/usr/bin/touch test_passed.Make it run every day at 21:30
```
sudo crontab -e
30 21 * * * /usr/bin/touch test_passed
```
- Add an anacron job with the following specifications:
A. It should run once every 10 days
B. It should have 5 minutes of delay
C. The job id should be db_cleanup
D. The command to run is: /usr/bin/touch /root/anacron_created_this
```
sudo vim /etc/anacrontab
10 5 db_cleanup /usr/bin/touch /root/anacron_created_this
```
- Using root user, schedule below given command to run at 15:30 August 20 2024 by using at utility:
```
sudo -i
at '15:30 August 20 2024'
Add /usr/bin/touch atscheduler the press ctrl+D
```
- Using crontab utility add a cron for user root to run below given command:/usr/bin/touch weeklyMake it run at 11:00AM on every Sunday
```
sudo crontab -e
0 11 * * 0 /usr/bin/touch weekly
```
- Add a cron for bob user to execute sudo systemctl restart nginx command on Sundays every week at 6am and 11pm.
```
0 6,23 * * 0 sudo systemctl restart nginx
```