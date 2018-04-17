---
layout: project
title: Project
subtitle: Password Updater
icon: fa-gear
projectNum: 2
---

Among my responsibilities at *Absolute Software* I was tasked with designing and building a powershell script that connected to a list of windows servers and check their local passwords against a password repository. The script took the following steps:

1. Read the list of inputted cnames and divided them into an array.
2. Connected to the PasswordState repository via API.
2. For each cname the script attempted to connect to the machine.
    1. If the connection fails, an error messages is displayed and Powershell moves on to the next cname.
3. Powershell parses the net user command on the machine and creates an array of local users.
4. For each user on the machine, Powershell will contact the PasswordState server and pull the password connected to the user and machine.
    1. If there is no password on record:
        1. Powershell will create a new entry in PasswordState and call the API to generate one
        2. Powershell will change the new account to the generated password.
        3. If the password API fails for any reason, an error message is generated and the password is not changed.
    2. If there is a password:
        1. Powershell will attempt to log on using this password.
        2. If log on is a success a success message is thrown and we move on to the next account.
        3. if log on fails, we generate a new password and apply it to the account, then test that we can log on again.
* * *

This script also provided other functions such as accepting either a .txt or inline cname for input, a feature that only returned the result and didn't change passwords, and a feature returned the names of systems it could access from a list. A similar version of this password updater script was implemented to do the same thing with Drac systems. 

When I first started with this project I hadn't ever used Powershell, but after only some researching and using the skills I learned in programming, I was able to create a functional program that could be easily modified and used repeatedly.