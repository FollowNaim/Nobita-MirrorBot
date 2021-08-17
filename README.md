[![Nobita](https://telegra.ph/file/446a798a9ac1b8c9db91d.png)](https://youtu.be/Pk_TthHfLeE)

# Nobita Mirror Bot
![GitHub Repo stars](https://img.shields.io/github/stars/breakdowns/slam-mirrorbot?color=blue&style=flat)
![GitHub forks](https://img.shields.io/github/forks/breakdowns/slam-tg-mirror-bot?color=green&style=flat)
![GitHub contributors](https://img.shields.io/github/contributors/breakdowns/slam-tg-mirror-bot?style=flat)
![GitHub watchers](https://img.shields.io/github/watchers/breakdowns/slam-tg-mirror-bot)
![Docker Pulls](https://img.shields.io/docker/pulls/breakdowns/mega-sdk-python?label=Docker%20Pull)
[![Contactl](https://img.shields.io/badge/Contact%20Mel-!-red)](https://t.me/nobita_o)

**Nobita Mirror Bot** is a _multipurpose_ Telegram Bot writen in Python for mirroring files on the Internet to our beloved Google Drive.

# Features supported:
<details>
    <summary><b>Click Here For More Details</b></summary>

## Additional Features
- qBittorrent supported
- Updater (**NOTE**: You must upload your **token.pickle** to Index and fill your **token.pickle** url to **TOKEN_PICKLE_URL**, because your **token.pickle** will deleted after update, for more info please check [Setting up config file](https://github.com/breakdowns/slam-tg-mirror-bot/tree/master#setting-up-config-file))
- Limiting size Torrent/Direct, Tar/Unzip, Mega, cloning Google Drive support
- Stop duplicate cloning Google Drive & mirroring Mega support
- Tar/Unzip Google Drive link support
- Select files before downloading
- Sudo with Database support
- Extracting **tar.xz** support
- Counting Google Drive link
- Heroku config support
- View Link button
- Shell and Executor
- Speedtest
- Torrent search Supported:
```
nyaa.si, sukebei, 1337x, piratebay,
tgx, yts, eztv, torlock, rarbg
```
- Direct links Supported:
```
letsupload.io, hxfile.co, anonfiles.com, bayfiles.com, antfiles,
fembed.com, fembed.net, femax20.com, layarkacaxxi.icu, fcdn.stream,
sbplay.org, naniplay.com, naniplay.nanime.in, naniplay.nanime.biz, sbembed.com,
streamtape.com, streamsb.net, feurl.com, pixeldrain.com, racaty.net,
1fichier.com, 1drv.ms (Only works for file not folder or business account),
uptobox.com (Uptobox account must be premium), solidfiles.com
```

## From Original Repos
- Mirroring direct download links, Torrent, and Telegram files to Google Drive
- Mirroring Mega.nz links to Google Drive (If your Mega account not premium, it will limit 5GB/6 hours)
- Copy files from someone's Drive to your Drive (Using Autorclone)
- Download/Upload progress, Speeds and ETAs
- Mirror all Youtube-dl supported links
- Docker support
- Uploading to Team Drive
- Index Link support
- Service Account support
- Delete files from Drive
- Shortener support
- Custom Filename (Only for URL, Telegram files and Youtube-dl. Not for Mega links and Magnet/Torrents)
- Extracting password protected files, using custom filename and download from password protected Index Links see these examples:
<p><a href="https://telegra.ph/Magneto-Python-Aria---Custom-Filename-Examples-01-20"> <img src="https://img.shields.io/badge/see%20on%20telegraph-grey?style=for-the-badge" width="190""/></a></p>

- Extract these filetypes and uploads to Google Drive
```
ZIP, RAR, TAR, 7z, ISO, WIM, CAB, GZIP, BZIP2, 
APM, ARJ, CHM, CPIO, CramFS, DEB, DMG, FAT, 
HFS, LZH, LZMA, LZMA2, MBR, MSI, MSLZ, NSIS, 
NTFS, RPM, SquashFS, UDF, VHD, XAR, Z.
```

</details>

## Setting up config file
<details>
    <summary><b>Click Here For More Details</b></summary>

### Required Field
- **BOT_TOKEN**: The Telegram bot token that you get from [@BotFather](https://t.me/BotFather)
- **TELEGRAM_API**: This is to authenticate to your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org DO NOT put this in quotes.
- **TELEGRAM_HASH**: This is to authenticate to your Telegram account for downloading Telegram files. You can get this from https://my.telegram.org
- **OWNER_ID**: The Telegram user ID (not username) of the Owner of the bot
- **GDRIVE_FOLDER_ID**: This is the folder ID of the Google Drive Folder to which you want to upload all the mirrors.
- **DOWNLOAD_DIR**: The path to the local folder where the downloads should be downloaded to
- **DOWNLOAD_STATUS_UPDATE_INTERVAL**: A short interval of time in seconds after which the Mirror progress message is updated. (I recommend to keep it `5` seconds at least)  
- **AUTO_DELETE_MESSAGE_DURATION**: Interval of time (in seconds), after which the bot deletes it's message (and command message) which is expected to be viewed instantly. (**Note**: Set to `-1` to never automatically delete messages)
- **UPSTREAM_REPO**: Link for Bot Upstream Repo, Dont Change it, fill `https://github.com/nobita-o/Nobita-Mirror-Bot`.
- **UPSTREAM_BRANCH**: Don't Touch it, fill `master`.
### Optional Field
- **ACCOUNTS_ZIP_URL**: Only if you want to load your Service Account externally from an Index Link. Archive your Service Account json files to a zip file directly (don't archive the accounts folder. Select all the jsons inside and zip them only instead. Name the zip file with whatever you want, it doesn't matter). Fill this with the direct link of that file.
- **TOKEN_PICKLE_URL**: Only if you want to load your **token.pickle** externally from an Index Link. Fill this with the direct link of that file.
- **DATABASE_URL**: Your Database URL. See [Generate Database](https://github.com/breakdowns/slam-tg-mirror-bot/tree/master#generate-database) to generate database (**NOTE**: If you use database you can save your sudo id permanent using `/addsudo` command).
- **AUTHORIZED_CHATS**: Fill user_id and chat_id (not username) of you want to authorize, Seprate them with space, Examples: `-0123456789 -1122334455 6915401739`.
- **SUDO_USERS**: Fill user_id (not username) of you want to sudoers, Seprate them with space, Examples: `0123456789 1122334455 6915401739` (**NOTE**: If you want save sudo id permanent without database, you must fill your sudo id there).
- **IS_TEAM_DRIVE**: Set to `True` if `GDRIVE_FOLDER_ID` is from a Team Drive else `False` or Leave it empty.
- **USE_SERVICE_ACCOUNTS**: (Leave empty if unsure) Whether to use Service Accounts or not. For this to work see [Using Service Accounts](https://github.com/breakdowns/slam-tg-mirror-bot#generate-service-accounts-what-is-service-account) section below.
- **INDEX_URL**: Refer to https://gitlab.com/ParveenBhadooOfficial/Google-Drive-Index The URL should not have any trailing '/'
- **MEGA_API_KEY**: Mega.nz api key to mirror mega.nz links. Get it from [Mega SDK Page](https://mega.nz/sdk)
- **MEGA_EMAIL_ID**: Your email id you used to sign up on mega.nz for using premium accounts (Leave th)
- **MEGA_PASSWORD**: Your password for your mega.nz account
- **BLOCK_MEGA_FOLDER**: If you want to remove mega.nz folder support, set it to `True`.
- **BLOCK_MEGA_LINKS**: If you want to remove mega.nz mirror support, set it to `True`.
- **STOP_DUPLICATE**: (Leave empty if unsure) if this field is set to `True`, bot will check file in Drive, if it is present in Drive, downloading or cloning will be stopped. (**Note**: File will be checked using filename, not using filehash, so this feature is not perfect yet)
- **CLONE_LIMIT**: To limit cloning Google Drive (leave space between number and unit, Available units is (gb or GB, tb or TB), Examples: `100 gb, 100 GB, 10 tb, 10 TB`
- **MEGA_LIMIT**: To limit downloading Mega (leave space between number and unit, Available units is (gb or GB, tb or TB), Examples: `100 gb, 100 GB, 10 tb, 10 TB`
- **TORRENT_DIRECT_LIMIT**: To limit the Torrent/Direct mirror size, Leave space between number and unit. Available units is (gb or GB, tb or TB), Examples: `100 gb, 100 GB, 10 tb, 10 TB`
- **TAR_UNZIP_LIMIT**: To limit mirroring as Tar or unzipmirror. Available units is (gb or GB, tb or TB), Examples: `100 gb, 100 GB, 10 tb, 10 TB`
- **VIEW_LINK**: View Link button to open file Index Link in browser instead of direct download link, you can figure out if it's compatible with your Index code or not, open any video from you Index and check if the END of link from browser link bar is `?a=view`, if yes make it `True` it will work (Compatible with [Bhadoo Index](https://gitlab.com/ParveenBhadooOfficial/Google-Drive-Index) Code)
- **UPTOBOX_TOKEN**: Uptobox token to mirror uptobox links. Get it from [Uptobox Premium Account](https://uptobox.com/my_account).
- **HEROKU_API_KEY**: (Only if you deploying on Heroku) Your Heroku API key, get it from https://dashboard.heroku.com/account.
- **HEROKU_APP_NAME**: (Only if you deploying on Heroku) Your Heroku app name.
- **IGNORE_PENDING_REQUESTS**: If you want the bot to ignore pending requests after it restarts, set this to `True`.
- **STATUS_LIMIT**: Status limit with buttons (**NOTE**: Recommend limit status to `4` tasks max).
- **IS_VPS**: (Only for VPS) Set it to `True` if you use VPS
- **SERVER_PORT**: (Only for VPS) Your VPS port
- **BASE_URL_OF_BOT**: (Required for Heroku) Valid BASE URL of where the bot is deploy. Ip/domain of your bot like `http://myip` or if you have chosen other port then `80` then `http://myip:port`, for Heroku fill `https://yourappname.herokuapp.com` (**NOTE**: No slash at the end)
- **SHORTENER_API**: Fill your Shortener api key if you are using Shortener.
- **SHORTENER**: if you want to use Shortener in Gdrive and index link, fill Shortener url here. Examples:
```
exe.io, gplinks.in, shrinkme.io, urlshortx.com, shortzon.com
```

Above are the supported url Shorteners. Except these only some url Shorteners are supported.
### Add more buttons (Optional Field)
Three buttons are already added of Drive Link, Index Link, and View Link, you can add extra buttons, if you don't know what are below entries, simply leave them, don't fill anything in them.
- **BUTTON_FOUR_NAME**:
- **BUTTON_FOUR_URL**:
- **BUTTON_FIVE_NAME**:
- **BUTTON_FIVE_URL**:
- **BUTTON_SIX_NAME**:
- **BUTTON_SIX_URL**:

</details>

## Deploying on Heroku

- Give stars and Fork this repo then upload **token.pickle** to your forks, or you can upload your **token.pickle** to your Index and put your **token.pickle** link to **TOKEN_PICKLE_URL** (**NOTE**: If you didn't upload **token.pickle** uploading will not work). How to generate **token.pickle**? [Read here](https://github.com/breakdowns/slam-tg-mirror-bot#getting-google-oauth-api-credential-file)
- Hit the **DEPLOY TO HEROKU** button and follow the further instructions in the screen
- Recommended to use 1 App in 1 Heroku accounts

<p><a href="https://heroku.com/deploy"> <img src="https://img.shields.io/badge/Deploy%20To%20Heroku-blueviolet?style=for-the-badge&logo=heroku" width="200""/></a></p>

# Using Service Accounts for uploading to avoid user rate limit

# Contact Me

[Telegram](https://t.me/nobita_o)

# Credits

All Credits Goes to:

[Nobita](https://t.me/nobita_o)
