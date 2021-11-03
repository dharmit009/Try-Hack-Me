# cron jobs 

> It a program which automatically execute commands when conditions are met. 

## Description
MIN  - 	What minute to execute at
HOUR -	What hour to execute at
DOM  - 	What day of the month to execute at
MON  -	What month of the year to execute at
DOW  -	What day of the week to execute at
CMD  -	The actual command that will be executed.

### Example

0 *12 * * * cp -R /home/cmnatic/Documents /var/backups/
