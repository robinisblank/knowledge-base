# Working with the Command-Line Interface

## Understanding the CLI
- All OSes offer a Command-Line Interface (CLI).
- A specific CLI is called a shell; most OSes provide multiple shell choices. In Windows, there is Command Prompt (CMD) and Windows PowerShell, and in Linux, there is the Bash shell.
- All shells have a prompt to type in commands.
- Almost all shells prevent you from running certain commands and can only be run by a higher privileged user (administrator or superuser) to protect your system.
- Many commands use command-line switches, also known as flags or options, to modify the function of a command.
- The `dir` command in Windows displays a list of files and subdirectories in a directory.
- The `/p` switch with the `dir` command pauses after each screenful of information.
- The `/?` switch and the `help` command provide help information for Windows commands. For example: `dir /?` and `help dir`.
- The `cls` command in Windows clears the screen.
- In Windows, you can open a shell as an administrator by clicking "Run as administrator". But in Linux, you can't. Instead, we use the `su` and `sudo` commands.
- The `su` command allows for a one-time superuser login. This practice is discouraged.
- The `sudo` command runs a command as the superuser. For example: `sudo ls`.
- The `ls` command in Linux lists directory contents.
- The `-l` option with the `ls` command enforces a long listing format.
- The `clear` command in Linux clears the screen.
- The `man` command provides a manual for Linux commands. For example: `man ls`.

## Navigating the CLI
- Use the `cd` (change directory) command in all OSes to move the prompt to different folders/directories.
- Every OS has a home directory where individual users go.
- `cd \` in Windows and `cd /` in Linux will take you to the root directory.
- `.` is where you are.
- `..` is the folder above where you are.
- `cd ..` will move you to one folder up.
- To change drives in Windows, type the drive letter and press Enter. For example: `d:`.
- You don't cd into a drive. You first get to the drive letter and then cd into folders.
- Changing drives will always bring you back to the folder you left in that drive.
- Linux doesn't use drive letters; instead, everything is mounted as folders under the root directory (`/`).
- Tab auto-fills available commands.
- `cd ~` in Linux will move you to the home directory.
- `pwd` in Linux will show you in what directory you are in.
- For navigation paths: Windows uses the backslash (`\`), and Linux uses the forward slash (`/`).

## Working with Folders
- Use the `md` (Windows) or `mkdir` (Linux) command to make a folder/directory.
- Windows is case-insensitive; Linux is case-sensitive.
- Use the `rd` (Windows) or `rmdir` (Linux) command to remove/delete an empty folder/directory.
- Use `rd /s` (Windows) or `rm -r` (Linux) to remove a directory and its contents.
- The up arrow key shows previous commands.
- The `mkdir` (make directory) and `rmdir` (remove directory) commands work in both Windows and Linux. However, `md` and `rd` are shorter aliases that only work in Windows.

## Working with Files
- Use the `del` (Windows) or `rm` (Linux) command to delete file(s).
- Use the `copy` (Windows) or `cp` (Linux) command to copy file(s).
- Use the `move` (Windows) or `mv` (Linux) command to move a file(s).
- Use wildcards to work with more than one file at a time.
- `*.txt` will run the command on all files with the `.txt` extension.
- `*.*` or `*` will run the command on all files.
- The best approach is to first cd into the source directory and then copy/move.
- Always check the destination to see if files got copied/moved in good order.

## Working with Drives
- The `format` command in Windows formats a disk for use with Windows.
- The `/FS:filesystem` switch with the `format` command specifies the type of the file system (FAT, FAT32, exFAT, NTFS, UDF, ReFS). For example: `format e: /FS:NTFS`.
- The `/Q` switch with the `format` command performs a quick format. For example: `format e: /FS:NTFS /Q`.
- The `chkdsk` command in Windows checks a disk and displays a status report. If you don't mention any drive letter, then it will check the drive you are in.
- The `/F` switch with the `chkdsk` command fixes errors on the disk. For example: `chkdsk d: /F`.
- System File Checker (SFC) scans the integrity of all protected system files and replaces incorrect versions with correct Microsoft versions.
- The `sfc /SCANNOW` command scans the integrity of all protected system files and repairs files with problems when possible.
- The `sfc /VERIFYONLY` command scans the integrity of all protected system files. No repair operation is performed.
- Deployment Image Servicing & Management (DISM) enumerates, installs, uninstalls, configures, and updates features and packages in Windows images.
- The `DISM /Online /Cleanup-Image /RestoreHealth` command targets the running OS, performs operations such as cleanup or repair on the system image, scans the image for corruption, and automatically fixes any issues it finds using available source files.
- SFC and DISM go hand in hand and the recommended sequence is:
	1. Run SFC first to fix minor system file issues.
	2. If SFC doesn't resolve the issue, run DISM to repair the image.
	3. Optionally, run SFC again to confirm that all file issues are resolved.
- `diskpart` is a command-line utility in Windows used for managing hard drives, partitions, and volumes. It's more powerful than the graphical Disk Management tool, offering advanced control over disk configurations.

## Super Copy Commands
- The `copy` command in Windows is designed for copying individual files or groups of files, but it doesn't support directories.
- `xcopy` is the original Windows tool to copy entire directories and subdirectories, making it suitable for larger file structures.
- The `/S` switch with the `xcopy` command copies directories and subdirectories except for empty ones.
- The `/E` switch with the `xcopy` command copies directories and subdirectories, including empty ones.
- The `/V` switch with the `xcopy` command verifies the size of each new file.
- The `/H` switch with the `xcopy` command copies hidden and system files also.
- `robocopy` (Robust File Copy) is a Windows command designed for high-reliability file transfers, including network transfers. It supports features like directory mirroring, resuming interrupted transfers, and copying file attributes and permissions, making it ideal for complex backup and synchronization tasks.
- The `/S` and `/E` switches are the same with the `robocopy` command as with the `xcopy` command.
- The `/Z` switch with the `robocopy` command copies files in restartable mode.
- The `/B` switch with the `robocopy` command copies files in Backup mode.
- The `/ZB` switch with the `robocopy` command uses restartable mode; if access is denied use Backup mode.
- The `/COPYALL` switch with the `robocopy` command copies all file info.
- The `/XA:H` switch with the `robocopy` command excludes files with the hidden attribute.
- We can use `robocopy` to copy files over a network, with the destination specified using a UNC path. For example: `robocopy C:\local_folder \\network_server\shared_folder /e /copyall /zb`.
- The `cp` command in Linux is ideal for everyday file operations, such as copying individual files or directories, preserving file attributes, and handling regular data.
- The `-r` option with the `cp` command copies directories recursively.
- The `-p` option with the `cp` command preserves file attributes.
- The `dd` (Data Duplicator) command in Linux copies data at a low level, byte by byte, often used for copying entire disks, partitions, or creating disk images. For example: `dd if=/dev/sda of=/dev/sdb`.
- For example to use the `dd` command to create image files: `dd if=/dev/sda1 of=~/backup.img`.
- For example to use the `dd` command to wipe the data on destination by writing zeroes: `dd if=/dev/zero of=/dev/sdb`.

## Command-Line Permissions
- The `icacls` command in Windows changes NTFS permissions.
- The `chmod` command in Linux changes the permissions of files and directories. For example: `chmod 777 filename`.
- The `ls -l` command in Linux lists files and directories with their permissions.
- Permissions in Linux are displayed as `drwxrwxrwx` where `d` represents a directory. If not a directory, then this will look like `-rwxrwxrwx`. Similarly, there will be a hyphen wherever that permission is turned off. The first three permissions are for the owner, the next three are for the group, and the last three are for others.
- `r` (read) is 4, `w` (write) is 2, and `x` (execute) is 1. You need to sum the numbers of the permissions you want to grant when using the `chmod` command.
- The first number in the `chmod` command sets permissions for the owner, the second number for the group, and the third for others.
- The `chown` command in Linux changes the owner and group of a file/directory. For example: `chown user:group filename`.
- The `passwd` command in Linux changes the user password.

## Advanced Windows Commands
- The `shutdown /s` command will shut down the computer.
- The `/r` switch with the `shutdown` command does a full shutdown and will restart the computer.
- The `tasklist` command displays a list of currently running processes on a local or remote machine.
- The `taskkill` command terminates tasks by Process ID (PID) or Image Name. For example: `taskkill /IM notepad.exe` and `taskkill /PID 1230 /PID 1241`.
- The `/F` switch with the `taskkill` command specifies to forcefully terminate the process(es).
- The `/T` switch with the `taskkill` command terminates the specified process and any child processes that were started by it.
- The `gpupdate` command refreshes Group Policy settings. It forces the system to apply any new or changed policies from Active Directory (if in a domain environment) or local policies.
- The `/force` switch with the `gpupdate` command reapplies all policy settings. By default, only policy settings that have changed are applied.
- The `gpresult` command displays the Resultant Set of Policy (RSoP) information for a target user and computer. It generates a report that shows detailed information about applied policies, including the source (domain or local) and the policy scope (user or computer). For example: `gpresult /R`.
- The `/R` switch with the `gpresult` command displays RSoP summary data. This is the minimum output that you can generate.

## Advanced Linux Commands
- The `shutdown` command is used to halt, power off, or reboot the machine.
- Without any time argument, the `shutdown` command will give you a minute before it shuts down the machine.
- The `shutdown now` command will immediately shut down the machine.
- The `-c` option with the `shutdown` command cancels a pending shutdown.
- The `-r` option with the `shutdown` command reboots the machine.
- `apt-get` and `apt` are both package management tools used in Debian-based Linux distributions.
- `apt-get` is an older, more comprehensive tool for package management, suitable for advanced users and scripts.
- `apt` is a newer, simplified interface designed for everyday package management with a user-friendly experience.
- The `apt-get update` command updates the package index on your system with the latest information from the repositories, allowing you to see available updates.
- The `apt-get install package-name` command installs the specified package along with any dependencies it requires.
- The `apt-get upgrade` command upgrades all currently installed packages to their latest versions without removing any packages.
- The `apt-get install --only-upgrade package-name` command upgrades the specified package only if it's already installed, without affecting other packages.
- The `apt-get remove package-name` command uninstalls the specified package from your system but leaves its configuration files intact.
- The `apt-get purge package-name` command uninstalls the specified package and removes its configuration files, effectively wiping it out from the system.
- The `apt-get autoremove` command cleans up your system by removing packages that were installed as dependencies but are no longer required.
- These commands will work similarly if you use `apt` instead of `apt-get`.
- The `ps` command displays information about currently running processes on the system.
- By default, `ps` shows processes associated with the current shell session (typically just the commands you’ve run from that terminal).
- The `ps aux` command displays a more detailed list of all running processes on the system, including those run by other users and background services. `a` lists processes from all users, `u` displays detailed information like the user, CPU, and memory usage, and `x` includes processes not attached to a terminal (daemon processes).
- The `ps aux | grep "string"` command will list processes including `string`.
- The `kill` command sends a signal (usually to terminate) to a process by its Process ID (PID). The default signal sent is `SIGTERM` (signal 15), which requests the process to terminate gracefully. For example: `kill 1234`.

## Introduction to Scripting
- A batch file is a plain text file in Windows that executes a series of commands in CMD.
- Batch files use `.bat` or `.cmd` file extension.
- The `set` command in Windows displays, sets, or removes cmd.exe environment variables. If used without parameters, it displays the current environment variables.
- In the CMD, we can access environment variables by enclosing them within the `%` symbol. For example: `cd C:%HOMEPATH%\Desktop`.
- A PowerShell script is a more advanced scripting language in Windows that can execute commands and perform complex automation tasks with more functionality than a batch file.
- PowerShell scripts use the `.ps1` file extension.
- Windows PowerShell Integrated Scripting Environment (ISE) allows users to create, run, test, and debug scripts and commands in Windows PowerShell.
- A cmdlet (pronounced "command-let") is a lightweight, specialized command that performs specific tasks in the PowerShell environment.
- A bash shell script is a script for Linux/Unix environments, written for the Bash shell.
- Bash shell scripts use the `.sh` file extension.

## Interpreted Languages
- In compiled languages, the source code is translated into machine code by a compiler before execution. This machine code is specific to the target system's architecture and needs to be recompiled for each platform.
- Once compiled, the machine code can be executed directly by the computer’s CPU without the need for the source code or the compiler.
- Executable files use the `.exe` extension.
- In interpreted languages, the source code is executed line by line by an interpreter without needing to be compiled into machine code beforehand.
- The interpreter reads and executes the code directly, translating each statement to machine code at runtime.
- Visual Basic uses the `.vbs` file extension.
- Python uses the `.py` file extension.
- JavaScript uses the `.js` file extension.

## Scripting and the Terminal
- The `hostname` command in Windows prints the name of the current host.
- `pathping` is a command-line network diagnostic tool in Windows that combines the functionality of both `tracert` and `ping`. It traces the route to a destination and provides detailed statistics about packet loss and latency at each hop.
- Time drift occurs when a computer's time gradually deviates from the correct time.
- OSes these days use Network Time Protocol (NTP) based on an atomic clock, and time drift is not an issue with atomic clocks.
- You can set up scripts to automate useful functions such as installing applications, remapping network drives, and scheduling backups.
- Always be cautious that your scripts don't inadvertently change system settings or cause a mishandling of resources.
- Triple-check the URLs used in a script and the script source to avoid unintentionally introducing malware.