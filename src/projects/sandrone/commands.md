---
order: 1000
label: All Commands
icon: ../../media/commands.png
---

# Commands

Everything Sandrone answers to. All of them are slash commands, so Discord will fill in the options for you as you type.

Angle brackets mean an option is required, square brackets mean it is optional. Nothing here is stored about you. The only command that leaves anything on disk is `/yt-dlp`, which hosts oversized downloads for a day; the [Privacy Policy](/projects/sandrone/privacy/) explains both.

## Bot

### `/stats`

Ping, uptime, hosting region, and the running version.

### `/links`

Every related link: inviting the bot, the support server, the website, and the source code.

### `/pcspecs`

The owner's setup, paged through with buttons: main PC specs, storage, peripherals, then laptop specs.

## People

### `/profile [user]`

A user's Discord profile, including status, pronouns, badges, and connected accounts. Defaults to you.

### `/uid [user]`

A user's Discord ID. Defaults to you.

## PluralKit

### `/pksystem [user]`

A user's PluralKit system: name, description, avatar, tag, and pronouns. Defaults to you.

### `/pkfront [user]`

Who's currently fronting in a user's PluralKit system. Defaults to you.

## Lookups

### `/github <username>`

Look up a GitHub user.

### `/repo <repository>`

Look up a GitHub repository, given as `username/repo`.

### `/codeberg <username>`

Look up a Codeberg user.

### `/wikipedia <query>`

Summarise a Wikipedia article. Results can be case-sensitive.

### `/urban-dictionary <query>`

Look up a definition on Urban Dictionary.

## Tools

### `/qr <text>`

Turn text or a URI into a QR code image.

### `/encrypt <input> [method]`

Encode text with Base64, Base32, ROT13, or a Caesar cipher. Defaults to Base64. The reply is only shown to you.

### `/decrypt <input> [method]`

Reverse one of those: decode Base64 or Base32, or undo ROT13 or a Caesar cipher. Defaults to Base64. The reply is only shown to you.

### `/yt-dlp <url> [type]`

Fetch a YouTube link as a video or audio file. Defaults to video.

A result that fits your server's upload limit is attached directly; a bigger one is hosted on the bot's server and linked instead, for 24 hours. Asking for the same video again within that window returns the same link and resets its timer.

Anything over the 2 GiB cap is refused.

### `/snippet <snip>`

Repost a commonly used explainer, covering the active developer badge, refreshing your client, PluralKit, plurality, and userproxies.

### `/tweet <url>`

Embed an X/Twitter post, video included, via a third-party proxy.

### `/bluesky <url>`

Embed a Bluesky post, video included, via a third-party proxy.

## Fun

### `/kitty`

A random cat.

### `/fungif <gif>`

One of a small set of cat GIFs, picked by name.

### `/explain-the-game`

You just lost the game.

### `/8ball <question>`

Ask Sandrone a yes-or-no question. Don't expect her to be nice about it.

## Genshin Impact

### `/genshin stats [account]`

Overview of an account: adventure rank, owned count, and how much is tracked live.

### `/genshin roster [account]`

Every character owned on an account, grouped by element.

### `/genshin main-chara <name>`

Character detail on the Main account, including weapon and artifacts.

### `/genshin alt-chara <name>`

The same, on the Alt account.

## Age-restricted 18+

Discord decides who may run these, and where, from your account's age setting and the channel's rating.

### `/nsfwgif <gif>`

An age-restricted GIF, picked by name.

## Owner only - restricted

These manage the bot itself and only answer to the owner. They are listed for completeness.

### `/cog list`

Show which command modules are loaded, and whether that survives a restart.

### `/cog load <name>`

Switch a command module back on.

### `/cog unload <name>`

Switch a command module off.

## Something missing?

Commands come and go as the bot gets worked on. The [bot's repository](https://github.com/doughmination/sandrone) is the source of truth, and questions are welcome in the [support Discord server](https://discord.gg/N8gCjS294R).
