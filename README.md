# mymonitor
My Monitor logs active X11 window over the time.


$ mymonitor -h
### NAME:
  mymonitor - My Monitor logs active X11 window over the time.

### SYNOPSIS:
  mymonitor [numberOfDaysAgo | -h]

### DESCRIPTION:
  My Monitor is a tool for micro-management.
  Why? It's helpful to think about how you spend your time.

  Motivation: remember things to fill boring work timesheets.

  Operation: this Bash script have two modules:
  
  - The logger: register in a log file (every second)
    the active window (software being used), 
    your PID, running parameters, actual title name, 
    and (wish) details about what is being done in it.

  - The summarizer: is called when the logger is already running.
    It compiles the summary files and shows the daily summary
    of the current date (or <numberOfDaysAgo> days ago).


### FILES CREATED:
  ~/mymonitor/mymonitor-<DATE>.<FORMAT>

  <DATE> is in format year-month-day (yyyy-mm-dd).
  <FORMAT> is:
    log - created by logger, updated every second.
    mm - created by summarizer. Squeeze and count repeated lines by minute
    hh - created by summarizer. Squeeze and count repeated lines by hour
    dd - created by summarizer. Summarize the day.
         Show minutes and seconds spent on each window (activity),
         grouped by hour and sorted by minutes.
         Also prints DATE, hour, PID, "command", "window name" and invoked "command line".

### AUTHORS:
  EdemarSantos <edemarsantos@gmail.com> - https://github.com/edemarsantos

### CHANGELOG:
  v1.0 2017-06-16 Initial production version.
  
  v1.1 2017-08-10 Beatifying and documentating code.
  
  v2.0 2017-09-29 Summary files in same path;
    File of daily summary, with minutes spent;
    Optional parameter "number of days ago" to print daily summary.

### WISHLIST:
  - Capture URL of Firefox browser.
  
  - Capture actual page in Zim Desktop Wiki.

### DEPENDENCIES:
  - For logger:
    xdotool - command-line X11 automation tool
    bash commands: pgrep date cat sed echo

  - For summarizer:
    bash commands: date cat sed echo sort uniq grep awk column

### TESTED ON:
  GNU bash, versão 4.3.48(1)-release (x86_64-pc-linux-gnu)
  
  xdotool version 3.20150503.1
  
  Ubuntu 16.04
