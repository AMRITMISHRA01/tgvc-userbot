# Telegram Voice Chat UserBot [![Mentioned in Awesome Telegram Calls](https://awesome.re/mentioned-badge-flat.svg)](https://github.com/tgcalls/awesome-tgcalls)

![Python Workflow](https://github.com/callsmusic/tgvc-userbot/actions/workflows/python-package.yml/badge.svg)

A Telegram UserBot to Play Audio in Voice Chats.

This is also the source code of the userbot which is being used for playing
DJ/Live Sets music in [VC DJ/Live Sets](https://t.me/VCSets) group.

Made with [tgcalls](https://github.com/MarshalX/tgcalls)
and [Pyrogram Smart Plugin](https://docs.pyrogram.org/topics/smart-plugins)

It's recommended to use [tgmusicbot](https://github.com/callsmusic/tgmusicbot)
along with this userbot.

<p align="center">
<b>𝗗𝗘𝗣𝗟𝗢𝗬𝗠𝗘𝗡𝗧 𝗠𝗘𝗧𝗛𝗢𝗗𝗦</b>
</p>

<h3 align="center">
    ─「 ᴅᴇᴩʟᴏʏ ᴏɴ ʜᴇʀᴏᴋᴜ 」─
</h3>


<p align="center"><a href="https://dashboard.heroku.com/new?template=https://github.com/AMRITMISHRA01/ResponseByAi.git"> <img src="https://img.shields.io/badge/Deploy%20On%20Heroku-bringle?style=for-the-badge&logo=heroku" width="220" height="38.45"/></a></p>



<h3 align="center">
    ─「 ᴅᴇᴩʟᴏʏ ᴏɴ ᴋᴏʏᴇʙ 」─
</h3>

<h3 align="center">
    
[![Deploy to Koyeb](https://www.koyeb.com/static/images/deploy/button.svg)](https://app.koyeb.com/deploy?name=dv-chatbot&type=git&repository=IamDvis%2FDV-CHATBOT&branch=main&builder=dockerfile&env%5BBOT_TOKEN%5D=&env%5BMONGO_URL%5D=&env%5BOWNER_ID%5D=&ports=8000%3Bhttp%3B%2F)

</h3>
## Introduction

**Features**

- Playlist, queue
- Loop one track when there is only one track in the playlist
- Automatically downloads audio for the first two tracks in the playlist to
  ensure smooth playing
- Automatically pin the current playing track
- Show current playing position of the audio

**Plugin**: vc.`player`

Commands only works in groups, userbot account itself and contacts can use any
commands, all members can use common commands after the userbot join the VC

1. Start the userbot, try `!ping`, `!uptime` or `!sysinfo` command to check if
   the bot was running
2. send `!join` to a voice chat enabled group chat from userbot account itself
   or its contacts, be sure to make the userbot account as group admin and give
   it at least the following permissions:
    - Delete messages
    - Manage voice chats (optional)
3. reply to an audio with `/play` to start playing it in the voice chat, every
   member of the group can use common commands such like `/play`, `/current`
   and `!help` now.
4. check `!help` for more commands

**Plugin**: vc.`channel`

Almost same as `player` plugin but commands only works in Saved Messages,
`!join` takes arguments to be able to join group or channel voice chats.

**Plugin**: `ping` and `sysinfo`

Commands only works for userbot account itself and its contacts.

## Requirements

- Python 3.6 or higher
- A
  [Telegram API key](https://docs.pyrogram.org/intro/quickstart#enjoy-the-api)
  and a Telegram account
- Choose plugins you need, install dependencies which listed above and run
  `pip install -U -r requirements.txt` to install Python package dependencies
  as well
- [FFmpeg](https://www.ffmpeg.org/)

## Run

Choose one of the two methods and run the userbot with
`python userbot.py`, stop with <kbd>CTRL+c</kbd>. The following example assume
that you were going to use `vc.player` and `ping` plugin, replace
`api_id`, `api_hash` to your own value.

### Method 1: use config.ini

Create a `config.ini` file

```
[pyrogram]
api_id = 1234567
api_hash = 0123456789abcdef0123456789abcdef

[plugins]
root = plugins
include =
    vc.player
    ping
    sysinfo
```

### Method 2: write your own userbot.py

Replace the file content of `userbot.py`

```
from pyrogram import Client, idle

api_id = 1234567
api_hash = "0123456789abcdef0123456789abcdef"

plugins = dict(
    root="plugins",
    include=[
        "vc.player",
        "ping",
        "sysinfo"
    ]
)

app = Client("tgvc", api_id, api_hash, plugins=plugins)
app.start()
print('>>> USERBOT STARTED')
idle()
app.stop()
print('\n>>> USERBOT STOPPED')
```

## Notes

- Read module docstrings of [plugins/](plugins) you are going to use at the
  beginning of the file for extra notes

## Self-hosting

This userbot should run fine on any cloud server. Popular choices of cloud
server providers are DigitalOcean, Vultr and Hetzner. You can use one of the
following referral links to sign up on Vultr to give the project author
credits in case you want to try Vultr.

<a href="https://www.vultr.com/?ref=7321667"><img src="https://www.vultr.com/media/banners/banner_728x90.png" width="728" height="90"></a>

Or [Give100get25 - Vultr](https://www.vultr.com/?ref=8559837-6G)

# License

AGPL-3.0-or-later

```
tgvc-userbot, Telegram Voice Chat Userbot
Copyright (C) 2021  Dash Eclipse

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```
