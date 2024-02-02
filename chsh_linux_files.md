# Files

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

## GNU Coreutils

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **ls**  |        | List directory contents                           |
| ^       | -h     | Human readable                                    | 
| ^       | -a     | List all files, including hidden                  | 
| ^       | -l     | Long format list                                  | 
| ^       | -d     | List directory names instead of contents          | 
| ^       | -S     | Sort by size                                      |
| ^       | -t     | Sort by time                                      |
| ^       | -r     | Reverse order                                     |
| ^       | -s     | Print allocated size of each file in blocks       |
| ^       | -1     | One file per line                                 |
| ^       | ./     | List contents one level deep                      |
| ^       | -i     | Get inode number of file (file id). Use `sudo find / -inum <number>` to find all links that point to the same file.|

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **cp**  |        | Copy files or directories                         |
|         | -r     | Copy directories recursively                       | 
|         | -i     | Prompt before overwriting files                    | 
|         | -u     | Copy only when the source file is newer or missing| 
|         | -n     | Do not overwrite existing files                    | 
|         | -a     | Archive mode (preserving ownership and permissions)| 
|         | -l     | Create hard links instead of copying               | 
|         | -s     | Create symbolic links instead of copying           | 
|         | -T     | Treat the destination as a file                     |
|         | -P     | Do not follow symbolic links in source              |
|         | -v     | Verbose mode (showing files as they are copied)    | 

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **rm**  |        | Remove files or directories                       |
|         | -r     | Remove directories and their contents recursively | 
|         | -i     | Prompt before every removal                        | 
|         | -f     | Force removal without confirmation                 | 
|         | -u     | Remove only when the file is newer or missing      | 
|         | -l     | Remove symbolic links only                         | 
|         | -d     | Remove empty directories                           | 
|         | -R     | Similar to -r, used for compatibility               |
|         | -P     | Overwrite regular files before deleting             |
|         | -W     | Attempt to undelete the named files                 |
|         | -v     | Verbose mode (showing files as they are removed)   | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **rmdir**|         | Remove empty directories                         |
|         | -p      | Remove parent directories as needed              | 
|         | -v      | Verbose mode (show removed directories)          | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **mkdir** |        | Create directories                                |
|         | -p      | Create parent directories as needed               | 
|         | -m      | Set the file mode (permissions) for the created directory | 
|         | -v      | Verbose mode (display the created directory)       | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **touch**|         | Change file timestamps or create empty files     |
|         | -c      | Do not create the file if it does not exist      | 
|         | -a      | Change only the access time                      | 
|         | -m      | Change only the modification time                  | 
|         | -t      | Set file time to specific value: (YYYYMMDDhhmm.ss) |
|         | -d      | Use a specified date/time                         | 
|         | -r      | Use the timestamp of another file                | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **ln**  |         | Create links to files and directories             |
| *syntax*|         | ln [options] {{path/to/file_or_directory}} {{path/to/symlink}}      |
|         | -s      | Create symbolic links (symlinks)                  | 
|         | -f      | Force. Remove existing destination files          | 
|         | -b      | Make a backup of the existing target file         | 
|         | -i      | Prompt before removing existing destination files | 
|         | -r      | Make relative symbolic links                      | 
|         | -T      | Treat the target as a normal file                  | 
|         | -v      | Verbose mode (show the files as they are processed)| 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **df**  |         | Report file system  disk space usage              |
|         | -h      | Human-readable format (KB, MB, GB)               | 
|         | -T      | Show filesystem type                              | 
|         | -t      | Limit the display to specific filesystem types   | 
|         | -i      | Display inode information                         | 
|         | -k      | Display sizes in kilobytes                        | 
|         | -m      | Display sizes in megabytes                        | 
|         | -P      | Output in POSIX format                            | 
|         | -x      | Exclude specific filesystem types                | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **du**  |         | Display disk usage of files and directories      |
|         | -h      | Human-readable format (KB, MB, GB)               | 
|         | -d      | Specify the depth of the display                 | 
|         | -c      | Display a grand total                             | 
|         | -s      | Display only a total for each argument           | 
|         | -a      | Show all files, not just directories             | 
|         | -k      | Display sizes in kilobytes                        | 
|         | -m      | Display sizes in megabytes                        | 
|         | -g      | Display sizes in gigabytes                        | 
|         | --exclude | Exclude specific directories or files            | 
|         | --max-depth | Print the total for each directory at most N levels deep | 
|         | --time  | Show time of the last modification                | 
|         | --help  | Display help information                           | 
|         | --version| Display version information                        |


## Other Non GNU Coreutils

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **tree**|         | List contents of directories in a tree-like format|
|         | -a      | All files are listed including hidden ones        | 
|         | -L      | Level of depth for directories to show             | 
|         | -d      | List only directories                             | 
|         | -f      | Display the full path prefix                      | 
|         | -i      | Don't print indentation lines                      | 
|         | -p      | Print the protections for each file                | 
|         | -s      | Print the size of each file                        | 
|         | -h      | Print human-readable file sizes                    | 
|         | -u      | Display file modification times                    | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **file**|         | Determine file type                               |
|         | -b      | Do not prepend filenames to output               | 
|         | -z      | Look inside a zipped file and determine the file type(s) inside  | 
|         | -L      | Follow symbolic links                             | 
|         | -i      | Determine the MIME encoding type of a file.       |
|         | --help  | Display help information                           | 
|         | --version| Display version information                        |

