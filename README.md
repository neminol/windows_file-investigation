# windows_file-investigation
Windows_file - nosteam.ro
(SAMPLE IS GIVEN, USE IT ON YOUR OWN)
Malware investigation on Windows_file

Date: 1/16/2022

Conducted by: github.com/neminol

BASIC INFORMATION ON THE VIRUS:

"Windows_file" is a password-protected .zip file found recently on the "nosteam.ro" website hosting cracked Steam games, such as "The Forest". It contains 2 files: "setup.exe" and a temporary file "tmp".

Under properties, setup.exe is "version 1.0.0.1". Every instance of "Windows_file" found is different which can be seen by comparison of the passwords for each instance.

EXECUTION OF THE VIRUS:

Prior executing the setup.exe file, it goes into the background of the Windows machine and executes several commands from different files.
While testing, we could see 3 .exe files being opened: "build.exe", "forfiles.exe" and "temp.exe". After execution of those 3 files, Windows Defender would initiate a warning on several common infections.

After that, a Powershell window is opened running commands as well, this time NOT triggering Windows Defender(due to its nature of not triggering antiviruses), and we could say that this is arbitrary code execution.
During inspection of the "setup.exe" file, we could as well classify it as a trojan.

AFTER "THE STORM":

After the execution of the virus, we could see several changes in our machine.
In the default browser, we could see a new extension. Now, in my case it was called "T-Cashback". We could notice that our machine was slower, so let's see which app uses the most.
In my case, it was "Youtube Downloader" which used 2.5 gigabytes of space. 


Using Malwarebytes(Premium Trial), I scanned the computer. I saw something I didn't really like. 351 infections, most of them spyware folders with cryptowallets.
Phew, I'm lucky I didn't do it on my main machine. That'd be horrible.
