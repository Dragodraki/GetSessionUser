# GetSessionUser
Get account name, SID and profile path of logged-in user session
(Release Date: 15.06.2024, Publisher: Dragodraki alias Dreamland, Notice: designed by me and no fork)

<br/>

[<img src="https://user-images.githubusercontent.com/76787321/197257488-1b7aa8e9-9b6f-4600-949e-8ff477cb4bf4.png" width="23%"></img>](https://github.com/Dragodraki/GetSessionUser/releases/latest/download/GetSessionUser.exe)

<br/>

If you run software, you often do this with another users account. Especially if you have limited user rights only (medium integrity level) per default and do not belong to administrator group: If you run a process that requires elevated rights, by typing in the user credentials of another user in UAC you not only borrow elevated token from another one but act fully as if you were logged on with that account. Microsoft does not know "Run with administrator rights" but only "Run as administrator (account)".

That will be a problem as soon you gathered elevated rights as said limited user from another one (e.g. program/game installation) and like to run/play after the wizard ends directly. In this case it will not use your environment variables to load/save settings but those from the one authenticated your elevation with. Another scanrio is when a windows service is run (always as root aka NT-System) but should interact with your personal desktop - it won't do it but use a non-existent desktop that belongs to the system user.

This program cannot undo this, but it can deetermine the original user for you. In IT we call it the session user that is logged on. Currently this method is only possible with a WMI query. With the information of the actual user (session) you might be able to patch your installer by yourself to use the correct environment.

Update: I have written another program that not only retrieve that information but also De-Elevate (or maybe better De-Runas) when starting a program you provde as parameter. It's much more powerful than this tool because it includes the ready patch for the problem mentioned above already: https://github.com/Dragodraki/RunUnElevated
