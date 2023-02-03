# Linux Task Automation

## Creating Bash Scripts

### 1. Create a .sh file
```
nano my_script.sh
```

### 2. Determine path for bash

```
which bash
```
### 3. Add path to shabang in script
`#!/usr/bin/bash`  
This tells the shell to interpret everything in the file as bash commands.  
### 4. Run script
```
bash my_script.sh
```
or...
```
chmod +x my_script.sh
my_script.sh
```

## Automating task with Cron
Edit your crontab:
```
crontab -e
```
### Scheduling syntax
<a href="crontab.guru" target="_blank" rel="noopener noreferrer">crontab.guru</a>

|Time interval| Options|
|------------|---------|
|minutes| 0-59 | 
|hours| 0-23 | 
|day of month| 1-31 | 
|month| 1-12 or JAN-DEC| 
|day of week| 0-6 or SUN-SAT| 

|Special Characters| Meaning|Example|
|------------|---------|------|
|*| any values | * |
|,| value list separator | 0,15,30,45 |
|-| range of values | 1-5 |
|/| step values | */15 |