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

## ⚠️ Important Note about Bash History

Whatever you type in Bash is usually saved in a history file (commonly `~/.bash_history`). This means all your commands are recorded.

- You can view them with:

```bash
history
```

- Be cautious: **sensitive data** (like passwords typed directly into commands) will also be stored here unless cleared.

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

⸻

✅ With these basics, you can already navigate, list files, create files, and understand where commands live in Linux!
