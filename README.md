# Modern Activity Detection for Just Natsuki

A fan-made player player activity detection upgrade and bug-fix for [Just Natsuki](https://github.com/Just-Natsuki-Team/NatsukiModDev) and built in Ren'Py 6.99, because (1) the script relied on overly-specific and sometimes buggy code, (2) the entire list was three years out of date, (3) Mac and Linux apps were vastly underrepresented, and (4) the vanilla feature was flat-out disabled on Mac altogether. 

(Fun fact: this was the second submod I ever wrote, like five months ago. I thought it was busted because these weird "Talk to me!" notifications kept coming through randomly, so I never released it into the wild—turns out those weren't a bug, just *how they were triggering* was. Just another casualty of running JN on Mac. Well, at least your old pal Zhaumbie's around.)


> [!WARNING]
> **This is an unofficial fan-made submod for Just Natsuki. It is not affiliated with the Just Natsuki team.**  
> The developers are **not responsible for troubleshooting this submod** or problems caused by installing it. This submod *does not touch your persistent file*, but backing it up is always the BEST idea.
>
> > Before installing, **please back up your persistent data:** [How to back up your JN persistent file](https://github.com/Just-Natsuki-Team/NatsukiModDev/wiki/04:-FAQ#can-i-back-up-my-save-data--how-do-i-find-my-persistent)

*Seriously please for the love of god it takes like zero effort, just back up your persistent file (it is a really good habit)*

___

## What is this?
**Just Natsuki** already contains a pretty robust activity detection system. It's a neat feature that's a fun little treat when it happens; Natsuki can comment through your system notifications on your desktop's active window and what you're doing, provided these five things are **all true at once**:

<details>
  <summary>Spoilers!</summary>
&nbsp;
  
1. Something other than JN is your active window, and;
2. Natsuki's code recognizes the active window, and;
3. This is exactly when her code checks, once per minute (the timer pauses during dialogue), and;
4. The active window has changed since her last comment, and;
5. With only a 5% chance of success.
</details>

### ...Except It's Broken(ish)~
Unfortunately, loads of the script's existing rules are in dire need of a tune-up. **For example**, for Natsuki to recognize "Steam", the entire captured window title **had to be exactly "Steam"**. Nothing before or after it. That means most Steam Library content and all of Steampowered.com and Steamcommunity.com were out, making the chances of detection basically zip—especially since Natsuki can't detect Steam games, only **exactly** a window titled "Steam". 

And if you're on macOS, good news! You probably didn't know this existed. Not only is **the entire system disabled**, but... of the only three Apple apps recognised, *one* stopped shipping on Macs **three years** before modern JN launched!

___

## Features
Since the mechanic's main flaw is Natsuki relies on a whitelist of recognised apps, programs, and websites that's years out of date, I've widely expanded that whitelist for **Windows, Mac, and Linux and the 2026 internet**. 

Without changing a thing about vanilla JN's mechanics, this submod...

- Strengthens JN’s existing activity categories

- Recognizes modern application names, window titles, and site addresses

- Adds **many** current popular Windows, macOS, and Linux programs

- Distinguishes similar services correctly (e.g. YouTube Music vs ordinary YouTube)

- Restores activity detection and system notifications on macOS

**For a full list of apps/programs/websites changed and added...**

<details>
  <summary>(I'm warning you—it's a doozy)</summary>
  
### Coding
- **Visual Studio**: Now finds the program name in more window-title layouts.
- **Notepad++**: Corrected a broken vanilla detection rule.
- **Vim**
- **Eclipse**
- **GitHub Desktop**: No longer requires the entire window title to be exactly "GitHub Desktop."
- **Atom**: No longer requires the program name to appear after a particular separator.
- **Brackets**: No longer requires the program name to appear after a particular separator.
- **Scratch**: No longer requires the program name to appear after a particular separator.
- **Sourcetree**: No longer requires the entire window title to be exactly "Sourcetree."

#### New
- Visual Studio Code
- Sublime Text
- Xcode
- Zed
- Kate
- Geany
- GNOME Builder
- Neovim
- CotEditor

___

### Discord
- **Discord**: Now recognizes both the desktop app and Discord pages opened in a browser.

#### New
- Discord Web

___

### Music Applications

- **Spotify**: Now accepts regular, Premium, and other common Spotify window titles.
- **iTunes**: No longer requires the entire window title to be exactly "iTunes." On modern macOS, Apple replaced it with the separate Apple Music, Apple TV, and Apple Podcasts apps.
- **Winamp**: No longer requires the entire window title to be exactly "Winamp."
- **MusicBee**: No longer requires the entire window title to be exactly "MusicBee."
- **AIMP**: No longer requires the entire window title to be exactly "AIMP."
- **Groove**: Microsoft replaced Groove Music with the newer Media Player app on Windows 11.
- **Zune**: Microsoft discontinued Zune; its music service was succeeded by Groove Music, which was later replaced by Media Player.

#### New

- Apple Music
- Apple Music Web
- YouTube Music: Extra protections prevent YouTube Music from being mistaken for ordinary YouTube.
- Amazon Music
- Amazon Music Web
- Tidal
- Deezer
- foobar2000
- Rhythmbox
- Marvis Pro

___

### Gaming

- **Steam**: Now recognizes the desktop app, Steam Store pages, and Steam Community pages instead of requiring a window named exactly "Steam."
- **Origin**: No longer requires the entire window title to be exactly "Origin." EA has replaced Origin on PC and Mac with the EA App.
- **Battle.net**: No longer requires the entire window title to be exactly "Battle.net."
- **itch.io**: No longer depends on one particular browser-title layout.

#### New

- Epic Games Launcher
- Xbox App
- EA App
- Ubisoft Connect
- GOG Galaxy
- Heroic Games Launcher
- Lutris
- Playnite

___

### YouTube

- **YouTube**: Now recognizes YouTube addresses, direct video pages, shortened `youtu.be` links, and Safari page information instead of depending on a title ending in "YouTube."

___

### Just Natsuki GitHub

- **Just Natsuki GitHub Repository**: Now recognizes the complete GitHub address and pages within the repository.

___

### Artwork

- **Adobe Photoshop**
- **Clip Studio Paint**
- **GIMP**
- **Krita**
- **Paint Tool SAI**
- **MediBang**
- **Paint.NET**: Corrected the rule so the dot in "Paint.NET" means an actual dot rather than any possible character.
- **Microsoft Paint**: Made more precise so unrelated titles containing "paint" are less likely to trigger it.

#### New

- Affinity Photo
- Affinity Designer
- Inkscape
- Pixelmator Pro
- Pixelmator
- FireAlpaca
- Corel Painter
- Pixiv
- ArtStation
- Newgrounds Art

___

### Anime Streaming

- **Crunchyroll**: Now recognizes series, episode, and other Crunchyroll pages instead of requiring a window named exactly "Crunchyroll."

#### New

- HIDIVE
- RetroCrush

___

### Work Applications

- **Microsoft Word**: Now recognizes the full application name and document windows ending in "Word."
- **Microsoft Excel**: Now recognizes the full application name and spreadsheet windows ending in "Excel."
- **Microsoft PowerPoint**: Now recognizes the full application name and presentation windows ending in "PowerPoint."
- **LibreOffice**
- **OpenOffice**

#### New

- Google Docs
- Notion
- Apple Pages
- Apple Numbers
- Apple Keynote

___

### Twitter

- **Twitter**: Now recognizes Twitter addresses and current window titles instead of depending on an outdated browser-title format.

#### New

- X
- Instagram Threads
- Bluesky
- Tumblr
- Mastodon

___

### DeviantArt

- **DeviantArt**: Now recognizes the DeviantArt address and current page titles instead of relying on two older title formats.

___

### Manga

- **MangaDex**: Now recognizes the MangaDex address directly instead of depending on one window-title layout.
- **MangaSee**: No longer requires its name to appear after a particular separator.
- **MangaKot**: No longer requires its name to appear after a particular separator.

#### New

- Manga Plus
- VIZ Shonen Jump
- VIZ Manga
- Webtoon
- Tapas
- Comikey

___

### ddlc.moe

- **ddlc.moe**: Now recognizes the actual website address while retaining the old page title as a fallback.

___

# Takeaway Food

- **Uber Eats**: Now recognizes its website address instead of depending on a particular page title.
- **DoorDash**: Now recognizes its website address instead of depending on a particular page title.
- **Grubhub**: Now recognizes its website address while retaining the old title format.
- **Deliveroo**: No longer depends on one exact page title.
- **Domino's**: Now recognizes its website address directly.
- **Pizza Hut**: Now recognizes its website address directly.

#### New

- Just Eat

___

### Instagram

- **Instagram**: Now recognizes the Instagram address and current page titles instead of depending on an old title containing a special bullet character.

___

### Music Creation

- **FL Studio**
- **GarageBand**
- **Logic Pro**
- **Pro Tools**
- **REAPER**
- **Cubase**
- **Studio One**
- **Cakewalk**: Cakewalk by BandLab reached end of life and was replaced by Cakewalk Sonar.
- **Mixcraft**

#### New

- Ableton Live
- Bitwig Studio
- Reason
- LMMS
- Ardour

___

### Reddit

- **Reddit**: Now recognizes Reddit addresses, posts, communities, and current page titles instead of depending entirely on the old "Reddit - Dive into anything" title.

___

### 4chan

- **4chan**: This is here because the devs coded it in for some reason. Vanilla only recognizes a window named exactly "4chan" or a title containing "- 4chan." It doesn't recognize the website address directly, and I've declined to improve the detection, especially since Natsuki lacks any dialogue to comment on it.

___

### Monika After Story

- **Monika After Story**: Now works when other text appears before the mod name instead of requiring the entire window title to match exactly.

___

### Just Yuri

- **Just Yuri**: Now works when other text appears before the mod name while retaining support for its beta title.

___

### Forever & Ever

- **Forever & Ever**: Now works when other text appears before the mod name instead of requiring the entire window title to match exactly.

#### New

- Just Sayori
- Just Sayori Mod

___

### Video Applications

- **VLC Media Player**: No longer requires the program name to appear after a particular separator.

#### New

- QuickTime Player
- Plex
- Jellyfin
- IINA
- mpv
- Infuse
- Celluloid

___

### E-Commerce

- **Amazon**: Now finds regional Amazon addresses anywhere in Safari's captured page information instead of expecting the title to begin with one.
- **eBay**: Now recognizes regional eBay addresses instead of depending on a specially formatted page title.

#### New

- Etsy
- AliExpress
- Temu

___

### Recording Software

- **OBS Studio**: Now recognizes OBS, OBS Studio, versioned titles, and windows ending in its name instead of requiring one narrow version-number format.
- **Bandicam**: No longer requires a four-digit number immediately after its name.
- **Fraps**: No longer requires the window title to begin with "Fraps."
- **XSplit Broadcaster**: No longer requires the entire window title to be exactly "XSplit Broadcaster."
- **Lightstream Studio**: No longer requires the window title to end with "Lightstream Studio."

#### New

- Streamlabs
- ScreenFlow
- Kooha
</details>

<details>
  <summary>tl;dr for my Linux peeps</summary>
  
#### These seemed fine so I left 'em alone
- Vim
- Eclipse
- GIMP
- Krita
- OpenOffice
- LibreOffice
- REAPER

#### These I improved detection for
- Atom
- Brackets
- Scratch
- Discord
- Spotify
- Steam
- itch.io
- VLC
- OBS Studio

#### These I added
- Kate
- Geany
- GNOME Builder
- Rhythmbox
- Lutris
- Ardour
- Celluloid
- Kooha
- ghostwriter
- Foliate
- Okular
</details>

---

## Installation

1. Back up your persistent file.

2. Download the latest release.

3. Copy everything inside the release's `game` folder into your Just Natsuki `game` folder.

4. To be clear, that means this .rpy will probably be in your `game/submods` folder.

5. Launch JN. You're done. Follow vanilla rules, it will fire off pretty rarely.

6. Have fun!


---

## Uninstallation

1. Delete the .rpy file.

2. Nope, that was it. You're already done.


---

## Bug reports

I can only test this myself on macOS, so I rely on Windows/Linux bug testers and beta testers. If you spot something amiss, please log an issue saying as much of this as possible:

- what happened
- the traceback, if the game threw one
- your operating system
- what other submods you have installed

Basically, as always, bring receipts.

---

## Credits

- Team Salvato for Doki Doki Literature Club
- The Just Natsuki Team for their work on Just Natsuki
- The folks in the JN Discord server for helping me realize what I thought was a bug was an intended feature, just firing off weirdly
