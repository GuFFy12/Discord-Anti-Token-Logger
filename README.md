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

  1. `npm install -g asar`
  2. `cd` `Appdata / Local / Discord \ app- (version) \ resources`
  3. `npx asar extract app.asar app`
  4. In the app folder that appears in this directory, edit the following files:

    4.1. app \ common \ moduleUpdater.js ===> Change skipHostUpdate = settings.get (SKIP_HOST_UPDATE) || ! updatable; ON skipHostUpdate = true;

    4.2. app \ common \ paths.js ===> Change userDataPath = determineUserData (userDataRoot, buildInfo); ON userDataPath = _path.default.join (_path.default.dirname (process.execPath), '..', 'data');
  
  5. `npx asar pack app app.asar`
  6. The app folder is not needed. You can delete.
  7. We start only with discord.exe which is installed in the folder of the version over which you performed the manipulations.
  8. After that, it is advisable to copy the Discord folder to another location and delete the discord through the built-in Windows uninstaller and delete the AppData / Roaming / discord and AppData / Local / Discord files.

AFTER INSTALLATION, CLOSE DISCORD DELETE AppData/Roaming/discord and AppData/Local/Discord FILES, THEN RUN DISCORD. EXCEPT AppData/Roamaning/discord/Dictionaries, NOTHING SHOULD APPEAR.

# Discord-anti-token-logger

Итак сегдня я раскажу как сделать из дискорда любой версии версию портабл с изменеными путям расположения файла с токеном.
После этих действий ваш файл с токенами будет недоступен для обычных токен логгеров дискорд.

РЕКОМЕНДУЕТСЯ УСТАНОВИТЬ ПАПКУ С ДИСКОРДОМ В ДРУГОЕ МЕСТО И ОБЯЗАТЕЛЬНО УДАЛИТЬ ФАЙЛЫ ДИСКОРДА В APPDATA (AppData/Roaming/discord and AppData/Local/Discord)

Вам предостовляется выбор:
1) Скачать готовую сборку с дискордом, установить ее и пользоваться. 
2) Скачать файл выше - напротив названия файла app.asar написанно для какой он версии дискорда.
3) Вручную распаковать app.asar, найти нужные файлы и строки, заменить их (мануал по этим операциям 
ниже).

Данный так назавем его патч включает в себя:
1) Изменение пути хранения файлов с токеном (по умолчанию appdata/roaming/discord) на директорию где установлен сам дискорд (Discord/data).
2) Отключение установки обновлений дискорда. Нужно это для того что бы патч в последствии не слетел при обновлении. 

Установка:

1-ый метод установки) Удалить дискорд через встроенный деинсталятор Windows и удалить файлы AppData/Roaming/discord and AppData/Local/Discord. Готовую сборку скачать и установить. Запускаемся только с ярлыка который лежит в основной папке.

2-ой метод установки) Файл app.asar установить в AppData/Local/Discord/app-(версия)/resources/ (заменить файл). После саму папку Discord желательно копировать в другое место и удалить дискорд через встроенный деинсталятор Windows и удалить файлы AppData/Roaming/discord and AppData/Local/Discord. Запускаемся только с discord.exe который установлен в папке версии над которой вы провели манипуляции.

3-ий метод установки) Вручную если вы не доверяете моему патчу.
  1. `npm install -g asar`
  2. `cd` `Appdata/Local/Discord\app-(version)\resources`
  3. `npx asar extract app.asar app`
  4. В появившийся в этой директории папке app правим следующие файлы:

    4.1. app\common\moduleUpdater.js   ===>   Меняем   skipHostUpdate = settings.get(SKIP_HOST_UPDATE) || !updatable;   НА   skipHostUpdate = true;

    4.2. app\common\paths.js           ===>   Меняем   userDataPath = determineUserData(userDataRoot, buildInfo);       НА   userDataPath = _path.default.join(_path.default.dirname(process.execPath), '..', 'data');
  
  5. `npx asar pack app app.asar`
  6. Папка app не нужна. Можете удалить.
  7. Запускаемся только с discord.exe который установлен в папке версии над которой вы провели манипуляции.
  8. После саму папку Discord желательно копировать в другое место и удалить дискорд через встроенный деинсталятор Windows и удалить файлы AppData/Roaming/discord and AppData/Local/Discord.

ПОСЛЕ УСТАНОВКИ ЗАКРОЙТЕ ДИСКОРД УДАЛИТЕ ФАЙЛЫ AppData/Roaming/discord and AppData/Local/Discord , ЗАТЕМ ЗАПУСТИТЕ DISCORD. КРОМЕ AppData/Roamaning/discord/Dictionaries НИЧЕГО ПОЯВИТСЯ НЕ ДОЛЖНО.
