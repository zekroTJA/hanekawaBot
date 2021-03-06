 <div align="center">
     <h1>~ ハネカワ ボット ~</h1>
     <h2>"hanekawaBot"</h2>
     <strong>A lightweight, configurable and extendable NodeJS<br>Discord Self-Bot for self hosting</strong>
 </div>

-----

## Disclaimer

If you decide to use this bot on your own Discord account(s), I will not be liable if your accounts are getting banned! Written in the Discord API TOS, self bot's are not allowed and, if they get detected, you will get banned!

<div align="center">

*"[...] Automating normal user accounts (generally called "self-bots") outside of the OAuth2/bot API is forbidden, and can result in an account termination if found." - quote [Discord Bots TOS](https://discordapp.com/developers/docs/topics/oauth2#bot-vs-user-accounts)*

</div>

Accoding to the disclaimer of [TheRacingLion's Self-Bot](https://github.com/TheRacingLion/Discord-SelfBot/blob/master/README.md#disclaimer-july-29) from 29th July, there are maybe some rules, you should really follow to don't getting banned with a self-bot:

*Following points are quotes of TheRacingLion's Self-Bot README:*

- "A selfbot must not, under any circumstance, respond to other user's messages. This means it should not respond to commands, should not autoreply to certain keywords, etc. You must be the only one that can control it."

- "A selfbot must not, under any circumstance, do "invite scraping". This is the action of detecting server invites in chat, and automatically joining a server using that invite."

- "As selfbots run under your account they are subject to the same Terms of Service. Meaning they should not spam, insult or demean others, post NSFW material, spread viruses or illegal material, etc. They have to follow the same rules that you follow."

---

## Please read this first before using

If you want to use this bot or the code of it in any way in your own projects, please read this before:  
[zekro Open Source Code Policy](https://gist.github.com/zekroTJA/adbce830d6c876661cb7d7244ecb19b8)

---

## Description

This is a little Discord Self-Bot *(that means, this is a bot script running on your private account token and not with a discord API Bot account)* I'm currently working on. This will be kind of a copy of my older projekt, the [senjouBot](https://github.com/zekroTJA/senjouBot), created in python, but which causes some nasty errors if you are running another bot with the same API. So I will recreate this bot in NodeJS.  
So don't be surprised if both bot projects will have same functions.

---

## Current Features

*{this is an argument} - ({this is an optional argument}) - {these|are|valid|argument|options} - [this is variable]*  
*So don't use any '{}' or '()' or '[]' or '||', it's just for explaining syntax.*

- **game**  
*Aliases:*  `g`  
*Usage:*  `>game ({name of game})`  
*No argument will reset the game status.*  
Change the displayed game message under your profile name.

- **embed**  
*Aliases:*  `e`  
*Usage:*  `>embed {content} ({c::[color]}) ({t::[title]})`  
*[color]: red, green, cyan, blue, violet, pink, gold, orange*  
*[title]: Use '_' instead of spaces. Like this: 'this_is_a_title'*  
Send your message as (optional) colored embed message with optional title.

- **status**  
*Aliases:*  `s`  
*Usage:*  `>status ({online|idle|dnd|invisible})`  
*No argument will reset your status to your client settings.*  
With this command, you can set your public status. If you set the game or start the bot only, It can cause that if you set your client status, other members will not see the new status. So you can reset this with this command or set your public status independently of your client status. So you can set your public status to 'online' and your client to 'dnd', so you won't get message notifications but you are visible as 'online'.

- **gif**  
*Usage:*  `>gif {search query} ({-[index]})`  
*[index]: Chose the index in search results by attaching for example '-1' or '-2' to the search query*  
Super fancy advanced gif command which can post super fancy crazy gifs from giphy.com in the chat by searching with a query and an optional index.

- **faq**  
*Usage:*  `>faq {list|[linkkey]}`  
*[linkkey]: One of the set keys for faq messages.*  
This is actually only a little command for myself, because I often get a lot of support questions where I need to send a link or something like that, so I have just a quick acces to this over this command.  
If you want to use it, just set your keys and messages in the `main.js` in the map `FAQS`.

- **clear**
*Usage:*  `>clear ({ammount})`  
With this command, you can delete up to 20 messages at once or just delete your last written message with just enetering `>c`.  
I don't recomment to overuse this command, because I dont know if you could get busted for that and if server owners like behaviour like this.  
*You can increase the message limit manually by editing the `cmds.coffee` script but you will only do this at your own risk!*

---

## Will be implemented:

- [ ] **Guild Info command**<br>*Display various information about guild*
- [ ] **User Info command**<br>*Display various information about user*
- [ ] **Secret Option**<br>*Command output only in console*
- [ ] **ID command**<br>*Display ID of object by mention or keyword*
- [ ] **Global Nickname command**<br>*Change your nickname on all servers*
- [ ] **Help Command**<br>*Returns all command invokes*
- [ ] **Logging in console / file**<br>*Write logs of commands in file and in console*
- [ ] **Stalking Command**<br>*Stalk someone that you get messages when someone goes online, write a message...*
- [x] **Json Settings system**<br>*Change aliases, prefix... in json file*
- [x] **Clear command**<br>*Only to clear own messages send by you*

---

## Setup

First you need to install NodeJS **(>= 6.x)** on your system.

**For Windows / MacOS**  
Just download and install [this installer](https://nodejs.org/en/download/) on your system.

**For Linux / Debian / ...**  
```bash
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```
Alternatively for Node.js 8:
```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```
Maybe you need to install curl before:  
```bash
sudo apt-get install curl
```

Then, you can just [download the repository](https://github.com/zekroTJA/hanekawaBot/archive/master.zip) to a folder on your system or clone it with git:
```bash
git clone https://github.com/zekroTJA/hanekawaBot.git
```

Now, you can install all needed packages with
```
npm i
```

Then open the **`config.json`** file and enter your **private account token** (not a bot account token!).  
*If you don't know how to get your private account token, just take a look below.*  
You can also change the prefix of the bot *(defaultly it's `>`)* and the FAQ-Links from FAQ-Command.  
Also you can change there all command invokes and aliases like you want!  

Little thing about the giphy API token:  
You don't need to enter a token if you don't have a giphy account, but if you have an account, please create a private giphy API token **[here](https://developers.giphy.com/dashboard/)**.  
Otherwise, the bot will run on an public beta API key, which is not save that it will work forever and may be terminated for function. So please create an account and use your own token.


After that, start the bot with
```
npm start
```
or with
```
node main.js
```

If you want to run it 24/7, maybe on a VPS, I recommend running the bot in a screen.  
If you have not installed screen yet, do it with
```bash
sudo apt-get install screen
```
Then you can run it in the screen with the command
```bash
screen -L -S self npm start
# Parameter -L creates a logfile named 'screenlog.0'
# Parameter -S self gives the screen the name 'self' that you can
# resume the screen with 'screen -r self'
```

---

## Getting private account token

1. Open your desktop discord client
2. Press `[STRG]` + `[SHIFT]` + `[I]` to open developer tools
3. Navigate to tab `Application`
4. Click on the left side on `Local Storage` -> `https://discordapp.com`
5. In the table, search for the key `token` and copy your token

---

## Implementing own commands

If you want to implement your own commands into the bot, you can do this adding your code to the `cmds.coffee` script as following:
```coffee
exports.yourcommandname = (msg, args) ->
    # out of msg you can grab all stuff like channel, member, author, content usw...
    # args containing commands args which were seperated by spaces
```
Then, go into `config.json` and add your new command that you can set invokes for it:
```json
"commands": {
    "yourcommandname": ["your", "command", "invokes"]
}
```
Finaly, you need to link them in `main.js` by adding entry like following **below the `COMMANDS = {}` definition**:
```js
bindCmd(confcmds["yourcommandname"], cmds.yourcommandname);
```
You can also feel free to **contribute** your new command to this repository, if you want. ;)
