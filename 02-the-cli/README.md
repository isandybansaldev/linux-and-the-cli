# The CLI (Command Line Interface/Emulator)

A **text-based interface** where you type commands to interact with your computer. Unlike GUIs (Graphical User Interfaces), there are no buttons or windows — just text input/output.

### Examples:

- Terminal.app, iTerm2.app on macOS
- Command Prompt or PowerShell on Windows
- GNOME Terminal on Linux

### Used for:

- Running commands like `ls`, `cd`, `git`, `ping`, `python`, etc.
- Managing files, installing software, compiling code

## Shell

A **program that runs inside the CLI**, interpreting your commands. Acts as the **middle layer** between you and the OS kernel.

### Common Shells:

| Shell Name                | Command | Used In             |
| ------------------------- | ------- | ------------------- |
| Bash (Bourne Again Shell) | `bash`  | Linux/macOS         |
| Zsh                       | `zsh`   | macOS (default)     |
| Fish                      | `fish`  | Linux/macOS         |
| PowerShell                | `pwsh`  | Windows/macOS/Linux |
| Cmd.exe                   | `cmd`   | Windows             |

### What it does:

- Reads your typed commands (e.g., ls -l)
- Parses and executes them
- Shows output in the terminal

🧠 Think of the Shell as the “brain” behind the CLI interface.

## **REPL - Read-Eval-Print loop**

An **interactive environment** where you type code (not just commands), and it **immediately runs and returns results**. Most often used in **programming languages**.

### Example (python):

```bash
$ python3
>>> 2 + 2
4
>>> print("hi")
hi
```

### Languages with REPLs:

- Python (`python3`)
- Node.js (`node`)
- Ruby (`irb`)
- JavaScript (in browser console)
- Clojure (`clj`)
- Java (`jshell`)

```
+---------------------------------------+
|  Terminal / CLI                       |
|                                       |
|  +---------------------------------+  |
|  | Shell (e.g. bash, zsh, cmd)        |  ← You run commands like ls, cd, mkdir
|  +---------------------------------+  |
|                                       |
|  +---------------------------------+  |
|  | REPL (e.g. python3, node, jshell)  |  ← You run code interactively
|  +---------------------------------+  |
+---------------------------------------+

```

# Linux Command Line Basics

Linux is very file-system-oriented — basically, everything is a file in Linux. You can always find out where you are in the file system by using the `pwd` command.

Before learning the commands, let’s clear up some important terminology.

⸻

## 📝 Arguments vs Flags

- **Argument** → Tells the command what to work on (like a file or folder name).
- **Flag (Option/Switch)** → Modifies how the command behaves.

Flags usually start with:

- `-` (short option)
- `--` (long option)

### Short Options

- Begin with `-` and are usually a single letter.
- Can be combined together.
- Example:

```bash
ls -l -a # same as ls -la
```

### Long Options

- Begin with -- and are usually full words.
- Cannot be combined.
- Example:

```bash
ls --all
```

### Example: `--help`

`--help` is a long option that shows the manual/help page for a command.

```bash
ls --help
```

### Example: `--ignore`

Some commands (like `ls`) support the `--ignore` option. It tells the command to **hide files matching a pattern or file**.

```bash
ls --ignore=*.txt
ls --ignore report.txt
ls -I report.txt
```

➡️ This will list files in the directory but skip any ending with `.txt`.

⸻

## 🔑 Common Linux Commands

### `echo $SHELL`

- Shows which shell you are currently using.

### `pwd`

- Prints the current working directory (your location in the file system).

### `cd`

- Change directory — lets you move between folders.
- `cd ..` -> go up one directory.
- `cd /` -> go to the root directory.
- `cd ~` -> go to home directory.

### `ls`

- Lists files and directories.
- `ls -l` -> shows detailed info (permissions, size, date, etc.).
- `ls -a` -> shows all files, including hidden ones.

Example:

```bash
ls home
```

- `ls` = command
- `home` = argument (the folder to list)

### `touch`

- Creates empty files or updates timestamps of existing ones.
- Examples:

```bash
touch notes.txt # create a file
touch -t 202508241530 report.txt # set timestamp to 2025-08-24 15:30
```

### `which`

- Shows the full path of a command/program.
- Example:

```bash
which ls
```

Might output: `/bin/ls`

**Note**: `bin` stands for **binary**, a directory where runnable programs are stored.

### `tail`

Shows the end of a file, by default last 10 lines

```bash
tail -n 20 file.txt # Shows the last 20 lines.
```

### `tail -f`

Follow mode, keeps showing new lines as they are added to the file (very useful for watching logs in real time).

```bash
tail -f file.txt # Keeps printing new lines as they are added.
```

### `head`

Shows the beginning of a file, by default 10 lines

```bash
head -n 20 file.txt # Shows the first 20 lines.
```

## ⚠️ Important Note about shell History

Whatever you type in your shell is usually saved in a history file (commonly `~/.bash_history` for bash). This means all your commands are recorded.

- You can view them with:

```bash
history
```

- Be cautious: **sensitive data** (like passwords typed directly into commands) will also be stored here unless cleared.

Generally, shell history is not saved in real time. It is buffered and only written to the history file when the session ends. To manually save the current session's history to the history file, you can run the `history -a` command.

## Tab Search

When you’re working in the **CLI (Command Line Interface)**, pressing the **Tab key** activates something called **tab-completion** (or auto-completion).

### Completes command names

```bash
ec<Tab> # echo
```

### Completes file/folder names

```bash
cd Doc<Tab> # cd Documents/
```

### Shows suggestions if multiple matches exist

```bash
ls scr<Tab> # script.sh  screenshot.png  scroll.txt
```

## Reverse Search

(**cmd** + **r**) allows you to search from your shell history instead of using arrow up and down for going back in shell history.

## Shortcuts

- **CTRL + A** - takes you to the beginning of the line
- **CTRL + E** - takes you to the end of the line
- **CTRL + K** - "yank" everything after the cursor
- **CTRL + U** - "yank" everything before the cursor
- **CTRL + Y** - "paste" (paste in quotes because it doesn't actually go into your system clipboard) everything you yanked
- **CTRL + L** - clear the screen
- **CTRL + R** - reverse search through history

## Signals

A signal is a notification that you send to a program. It's up to the program to understand what to do with that.

### CTRL + C (SIGINT)

If you hit CTRL + C while a program is running, you're telling it to interrupt what it's doing and stop. You'll use this constantly. One reason is some processes are designed to never quit until you send them a SIGINT to stop. A good example of that is the `yes` command. All `yes` does is spam the string "y" until you tell it to quit. A lazy programmer wrote it so it could automatically answer "yes" to all the prompts for interactive programs. (You can also say `yes n` or `yes whatever` and it'll spam whatever you want it to.)

So go type yes into your terminal. You'll find yourself with an infinite wall of ever-spamming ys in front of you. To stop it, hit CTRL + C and it'll stop immediately.

### CTRL + D (SIGQUIT)

Less useful but still good to know nonetheless is what CTRL + D does. Many programs won't respond to a SIGQUIT (some might, it's up to them) but bash itself will. If you're in a bash prompt and it want it to exit (like if you're remotely connected to a bash server for example), if you hit CTRL + D it'll tell the bash session to end. You also could close the window or just type `exit` and it'll exit too.

Note: Try CTRL + C first if it doesn't work use CTRL + D

### SIGTERM

There is no shortcut for SIGTERM but I wanted to make sure you knew it existed. If I use the `kill` program to kill another program, the way it does that is by sending a SIGTERM to the program. The difference is that if the program doesn't exit, kill will still shut down the process. We'll talk later about `kill` but know it's there.

### SIGKILL

If you want a program to stop and stop now, you can do `kill -9` (or `kill -SIGKILL`) and it will send the SIGKILL which means to the program "don't clean up, just stop as soon as possible.) Again, we'll cover this in a bit.

### More SIGNALS

There are many signals and I don't know what 10% of them do. If you run `kill -l` in your terminal, it'll show you all the signals your computer supports. Most of these are used for processes to communicate amongst each other or with the shell, like SIGALRM tell your emulator to make a beep. However only really the ones above you are the ones you care about.

⸻

✅ With these basics, you can already navigate, list files, create files, and understand where commands live in Linux!
