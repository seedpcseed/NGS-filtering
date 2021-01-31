---
id: e1644c53-37ba-4ac9-b3cf-4bdfef8323a7
title: Programming Notes and Shortcuts
desc: ''
updated: 1611935365248
created: 1611935365248
---
# SOS #sos

Running:

- jupyter notebook
  - copy the link given into a browser

# Run #linux commands in the background

This will run it in the background but still send messages to the terminal

```sh
command &
```

This will run the process silently 

```sh
command > /dev/null 2>&1 & 
```

Use the `jobs` utility to display the status of all stopped and background jobs in the current shell session:

```
jobs -l
```

The output includes the job number, process ID, job state, and the command that started the job:

```output
[1]+ 25177 Running                 ping google.com &
```

To bring a background process to the foreground, use the `fg` command:

```
fg
```

If you have multiple background jobs, include `%` and the job ID after the command:

```
fg %1
```

To terminate the background process, use the [`kill`](https://linuxize.com/post/kill-command-in-linux/) command followed by the process ID:

### Keep Background Processes Running After a Shell Exits

* * *

If your connection drops or you log out of the shell session, the background processes are terminated. There are several ways to keep the process running after the interactive shell session ends.

One way is to remove the job from the shell’s job control using the `disown` shell builtin:

```
disown
```

If you have more than one background jobs, include `%` and the job ID after the command:

```
disown %1
```

Confirm that the job is removed from the table of active jobs using the `jobs -l` command. To list all running processes, including the disowned use the [`ps aux`](https://linuxize.com/post/ps-command-in-linux/) command.

Another way to keep a process running after the shell exit is to use `nohup`.

The [`nohup`](https://linuxize.com/post/linux-nohup-command/) command executes another program specified as its argument and ignores all `SIGHUP` (hangup) signals. `SIGHUP` is a signal that is sent to a process when its controlling terminal is closed.

To run a command in the background using the `nohup` command, type:

```
nohup command &
```

The command output is redirected to the `nohup.out` file.

```output
nohup: ignoring input and appending output to 'nohup.out'
```

This will send the job to a  'quiet' place
nohup Rscript foo.R > ~/R/logs/foo.out 2>&1 &

If you log out or close the terminal, the process is not terminated

```
kill -9 25177
```

### Screen #screen

- `Ctrl+a` `c` Create a new window (with shell)
- `Ctrl+a` `"` List all window
- `Ctrl+a` `0` Switch to window 0 (by number )
- `Ctrl+a` `A` Rename the current window
- `Ctrl+a` `S` Split current region horizontally into two regions
- `Ctrl+a` `|` Split current region vertically into two regions
- `Ctrl+a` `tab` Switch the input focus to the next region
- `Ctrl+a` `Ctrl+a` Toggle between the current and previous region
- `Ctrl+a` `Q` Close all regions but the current one
- `Ctrl+a` `X` Close the current region
- `Ctrl+a` `d` detach
- screen -r resume session 

# Markdown

# #kali and #kaliGUI

In kali type the following

kex --esm --ip  -s

