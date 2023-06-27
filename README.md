# Fifa-23

Hey y'all! I got my Steam Deck less than a month ago and I've appreciated all of the guides and really the community support. When I got it I knew that EA's anti-cheat system for FIFA 23 doesn't play fair with Linux and even upon launching it says "Wine not supported". But I made it my mission to get this thing going... and I'm happy to report that I did!
Here's the steps I used start to finish, it's important to note that I'm using the EA App launcher for the game because I have EA Play through GamePass. It probably works with Origin too but I couldn't test it myself.
If you already have EA Play launcher installed skip to step 3, otherwise start from here and make sure you're in Desktop Mode for this:
Download EA Play through [NonSteam Launchers] (https://github.com/moraroy/NonSteamLaunchers-On-Steam-Deck) (shoutout to /u/steamdeckbro!). There's a nice tutorial on how to get setup here: https://steamdeckhq.com/tips-and-guides/install-3rd-party-launchers-on-steam-deck/
Run the EA Play app, log in, download FIFA 23
Once the installation is complete, quit the launcher, open your browser and download the FIFA 23 Live Editor (shoutout to /u/xAranaktu!) -- this will allow us to bypass EA's cheat at the cost of going online
Extract that directory somewhere within the proton prefix that contains your EA Play launcher. For me that was located in: "/home/deck/.local/share/Steam/steamapps/compatdata/NonSteamLaunchers/".
Right click "Launcher.exe" within the folder you just move and add it to Steam
Open Steam in Desktop mode and rightclick the new "Launcher.exe" game. In the "launch options" section set your STEAM_COMPAT_DATA_PATH to the proton prefix directory where you have your EA App installed. For me it's in /home/deck/.local/share/Steam/steamapps/compatdata/NonSteamLaunchers/. Then addd %command to the end. This is how my launch options looks like: STEAM_COMPAT_DATA_PATH="/home/deck/.local/share/Steam/steamapps/compatdata/NonSteamLaunchers/" %command%. Also be sure to force proton compatibility to the latest GE proton, for me it's GE-Proton8-3.
Launch "Launcher.exe" through steam. (Optional) When it launches, select "auto launch game", this will allow the Live Editor to launch FIFA every time you launch the launcher which is handy in Gaming Mode, but totally optional.
Press "Run Game". This will launch your EA Play app and launch FIFA. You should get to the splash screen! For me I had to spam random keys the first time to get it working.
Now if it didn't work completely here's some things that I encountered while trying to get it working:
Make sure you're not on a low wattage. My base profile is 4W so the game was struggling. I set it to 15 just to be safe but you can go down as low as 9w without issue I think.
Go into your proton prefix's documents folder and edit the fifasetup.ini file to both set it to the steam deck's resolution and also force a low graphical settings:
`
CONTROLLER_DEFAULT = 0
AUDIO_MIX_MODE = 0
CONFIG_APP_LOCALE = en-US
DIRECTX_SELECT = 0
FULLSCREEN = 1
MSAA_LEVEL = 1
RENDERINGQUALITY = 1
RESOLUTIONHEIGHT = 800
RESOLUTIONWIDTH = 1280
VOICECHAT = 0
WAITFORVSYNC = 1
WINDOWED_BORDERLESS = 0
STRAND_BASED_HAIR = 0
USE_GOAL_NETS_3D = -1
DYNAMIC_RESOLUTION = 0
WINDOWTITLE = "FIFA 23"
Also the way that live editor works is it pauses the game when it's invoked. and it's invoked on launch, so you'll have to hit "Window -> Hide Live Editor" for it to unpause the game and hide the live editor stuff. I tried mapping one of my buttons to "F9" but it doesn't work. Also for some reason in game mode I can move my mouse but I can't click on anything so I had to use the touchscreen to hide the editor.
And that's it! Now it should be noted that this doesn't run the best on steam deck. Gameplay itself you can hit 60 easy without any frame drops, but cinematics are a hot piece of garbage and has lots of frame drops and for some reason so does the menu. But hey, at least it works!
