# **Pandemic:** a ring3/userland rootkit based on dynamic linker (LD_PRELOAD) for hooking (g)libc functions!
	This is my first attempt at writing a userland rootkit that utilizes dynakic linker specifically, so be nice! This whole 
	thing is one giant learning process for me. Please, please, **PLEASE** don't even think of abusing this code for 
	any malicious/illegal pirpose(s) whasoever. Thanks, -MLT.

### **Compilation:**
```
gcc -o pandemic.c pandemic
``` 
*If direct usage of GCC/G++ is blocked, then try running my bash script "infect.sh" like so:*
```
git --clone repo
cd /directory-to-repo/
chmod +x infect.sh
./infect.sh
```


### **Usage:**
*This tool can either be used via command-line arguments, or through a primitive terminal-based user-interface*

###### **via command-line:**
```
./pandemic -flagsForHooks -C2_IP
``` 

*You can specify whether you want to hook particular libc functions, for example:*
```
./pandemic -c -1.3.3.7
``` 
*The above use acase would hook **ONLY** the "**connect();**" function on C2 IP address "**1.3.3.7**"
whereas the below use case would hook **BOTH** the "**connect();**" & "**accept();**" functions on C2 IP address "**23.45.56.68**"*
```
./pandemic -ca -23.45.56.68
``` 

*Leaving the value(s) for **-flagsForHooks** blank will cause the rootkit to automatically hook all system calls that it is capable of hooking!*


###### **via User-Interface:**
*As an alternative to passing command-line arguments to the tool at runtime, you are able to simply launch the program and then follow the on-screen instructions to tweak the rootkit's configuration to your liking. This is done via a combination of both **printf();** to output the (ASCII/ANSI-Based+Color) User Interface and **scanf();** to take user inputs as an alternative method to CLI-Args for reading inputs :)
