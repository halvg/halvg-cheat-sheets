# Bash

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

## Shortcuts

> Keys when in emacs mode. You can switch to 'vi' mode with 'set -o vi' command. Be back to emacs mode with 'set -o emacs'.

#### Movements

| Command    | Description                           |
|------------|---------------------------------------|
| Ctrl + a   | Go to beginning of line.              |
| Ctrl + e   | Go to end of line.                     |
| Ctrl + f   | Move forward one character.           |
| Ctrl + b   | Move backwards one character.         |
| Alt + f    | Move forward one word.                |
| Alt + b    | Move backwards one word.              |
{:.shortcuts-table}

#### Editing

| Command                          | Description                                              |
|----------------------------------|----------------------------------------------------------|
| Ctrl + k                         | Delete all characters after cursor.                      |
| Ctrl + u                         | Delete all characters before cursor.                     |
| Ctrl + w **or** Alt + Backspace  | Delete previous word or all characters of the word before cursor. |
| Alt + d                          | Delete next word or all characters of the word after cursor.|
| Ctrl + y                         | Paste previous deleted text.                             |
| Alt + u                          | Capitalize all characters in a word after the cursor.     |
| Alt + l                          | Uncapitalize all characters in a word after the cursor.   |
| Alt + .                          | Paste the last word of the previous executed command.     |
| Ctrl + l                         | Clears the screen and redisplay the line.                 |
| Ctrl + m                         | Enter. In practice same as RETURN.                        |
| Ctrl + j                         | Newline. In practice same as RETURN.                      |
| Ctrl + x, Ctrl + e               | Edit command in editor.                                   |
{:.shortcuts-table}

#### History

| Command    | Description                                              |
|------------|----------------------------------------------------------|
| !n         | Execute nth command in history.                          |
| !n:p       | Put the nth command in history without executing it. Then you can ctr+p and modify it. |
| !!         | Execute previous command.                                 |
| fc [n]     | Edit the nth command in history or the last one if there is no n param. |
| :cq        | Exit vi/vim without executing when editing with fc.      |
| history    | Show history.                                            |
| Ctrl + r   | Search history backward.                                 |
| Ctrl + p   | Fetch the previous command from the history list.         |
| Ctrl + n   | Fetch the next command from the history list.             |
| Ctrl + g   | Escape from history searching mode.                       |
| Ctrl + o   | Run the command found in history mode.                    |
{:.shortcuts-table}

#### Jobs

| Command      | Description                               |
|--------------|-------------------------------------------|
| Ctrl + z     | Suspends current command execution and moves it to the background. |
| jobs         | Prints currently running job              |
| bg <job_id>  | Put job in background                     |
| fg <job_id>  | Bring job to the foreground               |
| %n           | Job number n                              |
| %s           | Job whose command line starts with s      |
| %%           | Current job                               |
| %-           | Previous job                              |
{:.shortcuts-table}

## Bash built-in commands

| Command        | Explanation                                                                  |
| --------------- | ------------------------------------------------------------------------------ |
| `alias`         | Create or display aliases.                                                   |
| `bg`            | Run a suspended job in the background.                                       |
| `bind`          | Display or set key bindings for the current shell.                           |
| `break`         | Exit from a `for`, `while`, or `until` loop.                                 |
| `builtin`       | Run a shell built-in command.                                                |
| `case`          | Conditionally perform actions.                                               |
| `cd`            | Change the current working directory.                                         |
| `command`       | Run a command ignoring shell functions.                                      |
| `compgen`       | Display possible completions for a word.                                     |
| `complete`      | Specify how arguments should be completed.                                   |
| `continue`      | Resume the next iteration of a `for`, `while`, or `until` loop.             |
| `declare`       | Declare variables and give them attributes.                                  |
| `dirs`          | Display the list of remembered directories.                                  |
| `disown`        | Remove jobs from the shell's job table.                                      |
| `echo`          | Display a message on the screen.                                             |
| `enable`        | Enable or disable shell built-ins.                                           |
| `eval`          | Evaluate several commands/arguments.                                         |
| `exec`          | Replace the current process with a new one.                                  |
| `exit`          | Exit the shell with a specified status.                                      |
| `export`        | Set an environment variable.                                                 |
| `fc`            | Fix command.                                                                 |
| `fg`            | Run a job in the foreground.                                                 |
| `getopts`       | Parse positional parameters.                                                 |
| `hash`          | Remember the full pathname of a name argument.                               |
| `help`          | Display information about built-in commands.                                |
| `history`       | Display command history.                                                     |
| `if`            | Conditionally perform actions.                                               |
| `jobs`          | List active jobs.                                                            |
| `kill`          | Send a signal to a process.                                                  |
| `let`           | Perform arithmetic on shell variables.                                       |
| `local`         | Create a variable with local scope.                                          |
| `logout`        | Exit a login shell.                                                          |
| `popd`          | Remove the top directory from the stack and change to it.                    |
| `printf`        | Format and print data.                                                       |
| `pushd`         | Add a directory to the stack and change to it.                               |
| `pwd`           | Print the current working directory.                                         |
| `read`          | Read a line from standard input.                                             |
| `readonly`      | Mark variables or functions as read-only.                                   |
| `return`        | Exit a function with a specified status.                                    |
| `set`           | Set or unset shell options and positional parameters.                        |
| `shift`         | Shift positional parameters to the left.                                    |
| `shopt`         | Set and unset shell options.                                                 |
| `source`        | Execute commands from a file in the current shell.                          |
| `suspend`       | Suspend the shell execution.                                                 |
| `test`          | Evaluate conditional expressions.                                           |
| `times`         | Display the accumulated user and system times for processes run from the shell. |
| `trap`          | Trap signals and execute a command when they are received.                  |
| `type`          | Display information about command type.                                      |
| `typeset`       | Set attributes for variables.                                                |
| `ulimit`        | Set or display user-level resource limits.                                  |
| `umask`         | Set or display the file mode creation mask.                                 |
| `unalias`       | Remove an alias.                                                             |
| `unset`         | Remove variable or function names.                                           |
| `until`         | Loop construct.                                                              |
| `wait`          | Wait for a background process to finish.                                     |
| `while`         | Loop construct.                                                              |


