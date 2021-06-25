# Discord-anti-token-logger

So today I will tell you how to make a version of the portable from the discord of any version with changed paths for the file with the token.
After these steps, your file with tokens will be inaccessible for regular token loggers discord.

IT IS RECOMMENDED TO INSTALL THE DISCORD FOLDER IN A DIFFERENT LOCATION AND MANDATORY DELETE THE DISCORD FILES IN APPDATA (AppData/Roaming/discord and AppData/Local/Discord)

You are given a choice:
1) Download the ready-made assembly with discord, install it and use it.
2) Download the file above - opposite the file name app.asar it is written for what version of the discord it is.
3) Manually unpack app.asar, find the files and lines you need, replace them (the manual for these operations below).

This so-called patch includes:
1) Changing the path for storing files with the token (by default appdata/roaming/discord) to the directory where the discord itself is installed (Discord/data).
2) Disable the installation of discord updates. This is necessary so that the patch does not subsequently fly off during the update.

Installation:

1st installation method) Remove discord through the built-in Windows uninstaller and delete the AppData/Roaming/discord and AppData/Local/Discord files. Download and install the finished assembly. We start only from the shortcut that lies in the main folder.

2nd installation method) Install the app.asar file in AppData / Local / Discord / app- (version) / resources / (replace file). After that, it is advisable to copy the Discord folder to another location and delete the discord through the built-in Windows uninstaller and delete the AppData / Roaming / discord and AppData / Local / Discord files. We start only with discord.exe which is installed in the folder of the version over which you performed the manipulations.

3rd installation method) Manually if you don't trust my patch.
  1.` npm install -g asar`
  2.` cd` `Appdata / Local / Discord \ app- (version) \ resources`
  3. `npx asar extract app.asar app`
  4. In the app folder that appears in this directory, edit the following files:

    4.1. app \ common \ moduleUpdater.js ===> Change skipHostUpdate = settings.get (SKIP_HOST_UPDATE) || ! updatable; ON skipHostUpdate = true;

    4.2. app \ common \ paths.js ===> Change userDataPath = determineUserData (userDataRoot, buildInfo); ON userDataPath = _path.default.join (_path.default.dirname (process.execPath), '..', 'data');
  
  5. `npx asar pack app app.asar`
  6. The app folder is not needed. You can delete.
  7. We start only with discord.exe which is installed in the folder of the version over which you performed the manipulations.
  8. After that, it is advisable to copy the Discord folder to another location and delete the discord through the built-in Windows uninstaller and delete the AppData / Roaming / discord and AppData / Local / Discord files.

AFTER INSTALLATION, CLOSE DISCORD DELETE AppData/Roaming/discord and AppData/Local/Discord FILES, THEN RUN DISCORD. EXCEPT AppData/Roamaning/discord/Dictionaries, NOTHING SHOULD APPEAR.
