## CLI - Command Line Interface

A **text-based interface** where you type commands to interact with your computer. Unlike GUIs (Graphical User Interfaces), there are no buttons or windows — just text input/output.

💡 **Examples:**

- Terminal on macOS
- Command Prompt or PowerShell on Windows
- GNOME Terminal on Linux

🛠️ **Used for:**

- Running commands like `ls`, `cd`, `git`, `ping`, `python`, etc.
- Managing files, installing software, compiling code

## Shell

A **program that runs inside the CLI**, interpreting your commands. Acts as the **middle layer** between you and the OS kernel.

🐚 **Common Shells:**

| Shell Name                 | Command | Used In             |
| -------------------------- | ------- | ------------------- |
| Bash (Bourne Again Shell ) | `bash`  | Linux/macOS         |
| Zsh                        | `zsh`   | macOS (default)     |
| Fish                       | `fish`  | Linux/macOS         |
| PowerShell                 | `pwsh`  | Windows/macOS/Linux |
| Cmd.exe                    | `cmd`   | Windows             |

**What it does:**

- Reads your typed commands (e.g., ls -l)
- Parses and executes them
- Shows output in the terminal

🧠 Think of the Shell as the “brain” behind the CLI interface.

## **REPL - Read-Eval-Print loop**

An **interactive environment** where you type code (not just commands), and it **immediately runs and returns results**. Most often used in **programming languages**.

**Example (python):**

```bash
$ python3
>>> 2 + 2
4
>>> print("hi")
hi
```

🧪 **Languages with REPLs:**

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
