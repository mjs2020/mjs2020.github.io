---
layout: single
header:
  teaser: /assets/posts/2018-06-23-thunderbird-transfer/teaser.png
---
# Transfering Thunderbird profile and email archive from Windows to OSX

I've been a long term Thunderbird fan. Although I use it less and less for my daily email I still use it to keep my own email archive (with some emails dating back to 1998!).

I've recently transfered my profile from a Laptop where the profile was on a shared partition between Windows 10 and Ubuntu Linux to a MacBook Pro.

On Windows my profile folder was in:

```
C:\Users\Francesco\AppData\Roaming\Thunderbird\Profiles\xxxxxxxx.default
```

But my email was stored on a shared partition:

```
D:\Email
```

NOTE: On both Windows and OSX you can find the profile folder from Help -> Troubleshooting Information -> Profile folder

![Troubleshooting information](/assets/posts/2018-06-23-thunderbird-transfer/troubleshooting_information.png "Troubleshooting information")
![Profile folder](/assets/posts/2018-06-23-thunderbird-transfer/profile_folder.png "Profile folder")

On the MacBook my profile folder was in:

```
/Users/Francesco/Library/Thunderbird/Profiles/yyyyyyyy.default
```

And I wanted my email to be stored in

```
/Users/Francesco/Email
```

(The reason being I wanted to keep my data and my configuration separate and back them up to the cloud differently)

These are the steps I followed to move my profile and mail:

1) I copied my profile folder `xxxxxxxx.default` from my Windows machine to the Macbook placing it next to the existing profile `yyyyyyyy.default` and copied my email from `D:\Email` to `/Users/Francesco/Email`.
2) Opened the Thunderbird Profile Manager by running: `/Applications/Thunderbird.app/Contents/MacOS/thunderbird-bin -ProfileManager` from the terminal.
3) Select "Create new profile", choose a name for your profile and then click "Choose folder" select the folder you just copied.
4) At this point you're ready to start Thunderbird but your email location will be the interal folder in your profile. We will change this in the next step but to avoid downloading new messages to the wrong location I suggest you disable your network connection.
5) Start Thunderbird, your email will be missing. Open Tools -> Account Settings and change the location to your new folder. ![Mail location](/assets/posts/2018-06-23-thunderbird-transfer/mail_location.png "Mail location")
6) Thunderbird will restart and you're done.

You can optionally open the profile manager again to remove the previous default profile Thunderbird had created.