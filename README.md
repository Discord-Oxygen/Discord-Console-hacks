**Note:** I'm not affilated with Discord and do not encourage using any of these hacks. Use everything here at your own risk. This is meant for **educational purposes only** and using these codeblocks may result in your account being disabled/terminated.

# Community

<details>
  <summary>We're switching to Matrix!</summary>
  
Matrix is a community-based, decentralized, privacy friendly, end-to-end encrypted (super secure), uncensorable and open source messaging protocol, which unlike discord promotes custom clients and modifications. There are multiple different clients available, the most popular one (and also the refrence implementation) is Element. It runs on every OS and even has a pretty good web version. For more information check out https://matrix.org and https://element.io.<br>
I often get asked: "*If Matrix/Element is so super awesome, why didn't you start using earlier?*"<br>
Well actually I've been using Matrix for quite a long time now, Anonymous already switched to it many years ago. For me Matrix always has been something serious, I never really thought about using it for this Discord Stuff.
</details>

Here is the Invite Link to the community: https://matrix.to/#/#discord-oxygen:matrix.org

The main community is on matrix, most channels are encrypted and can only be accessed from within matrix.
For those of you who can't use Matrix we created the Discord Server, its bridged to the Community (=every message you sent in Discord automatically appears in matrix and vice-versa)<br>
Here's the Invite Link: https://discord.gg/2FqBxRA6fS (2nd server)<br>


Please don't use console hacks not sent by me, or you might risk loosing your account.<br>
I'll update this invite regularly, if e.g. my account gets compromised or Discord shuts down the Server, I will create a new Account, a new Server and will then update the invite above.<br>
If the invite doesn't work anymore, it means the Server got deleted and you need to wait until I can create a new Account.

# Inner workings of Discord

<details>
  <summary>Click here</summary>

## Discord Token Syntax

<details>
<table>
  <tr><th></th><th>Example</th></tr>
  <tr><td>User ID Encoded in Base64</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>Timestamp -epoch(1293840000) converted to base64</td><td>XCgboz</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>HMAC consiting of 27 chars (uppercase/lowercase letters, numbers, - or _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
</table>
There is this awesome diagram from <a href="https://github.com/hxr404/Discord-Console-hacks/issues/2">#2</a> wich shows the exact token structure:<br><br>
<img src="https://user-images.githubusercontent.com/34555296/120932740-4ca47480-c6f7-11eb-9270-6fb3fbbd856c.png"></img> <br>
</details>
<br>

## Discords Internal Server Structure

<details>
Check out this Article about Reverse Engineering Discord, and the proof that Discord acts as a MITM (Intercepts your traffic and decrypts your messsages): <a href="https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626">https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626</a><br>
That means, Discord Staff can read all of your messages... (still better than Telegram, where anyone can read your messages xD)<br>
If you need privacy, use Signal or Threema or Briar. (or all of them :)

![grafik](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)

<br>
<sup>How sending Audioo/Video Messages in Discord Works.</sup>
</details>
<br>
</details>
<br>

# Console Hacks

<details>
  <summary>Click here</summary>
  

## Be Careful!

As stated in my Disclaimer I don't promote using any kind of client modifications. Please don't use the code found here for illegal / hacking purposes, or you might risk seeing this error message:<br>

![image](https://user-images.githubusercontent.com/55095883/134189043-4da003de-4829-4d60-888a-6014ebb5c2b8.png)

  

## How to use these Hacks

It only works on Desktop Versions (Windows, Linux, MacOS), not on Mobile
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is electronjs wich is basically google chrome)
2. Click on "Console" if not already selected
3. Paste the script in
4. Press enter

## Obtaining your Token

<details>
<summary>Copies your Token into the Clipboard.</summary>

paste this into the Console (while being logged in)

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {return copy(m.default.getToken())}if (m.getToken !== undefined) {return copy(m.getToken())}}}]); console.log("%cWorked!", "font-size: 50px"); console.log(`%cYou now have your token in the clipboard!`, "font-size: 16px")
```

The token should be in your Clipboard.
</details>
<br>

## Logging in using Token

<details>
<summary>Modifies the Login screen so you can use Tokens to log in.</summary>

paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)

```js
function login(e) {setInterval(() => {window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.setToken !== undefined) {return m.default.setToken(e)}if (m.setToken !== undefined) {return m.setToken(e)}}}]);console.log("%cWorked!", "font-size: 50px");}, 50), setTimeout(() => {window.location.reload()}, 2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-_djjkz input-cIJ7To")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-AtZOdT button-3k0cO7 button-38aScr lookFilled-1Gx00P colorBrand-3pXr91 sizeLarge-1vSeWK fullWidth-1orjjo grow-q77ONN")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-32qID7")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-2KCXvj size14-e6ZScH h5-18_1nd title-3sZWYQ defaultMarginh5-2mL-bP")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-aR7y1d qrLogin-1AOZMt")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-3huAjp")[0]).parentElement.removeChild(element);
```

and log in<br>
Note that this doesn't work with Bot tokens, Bot tokens are different than user tokens, and Discord doesn't support this.<br>
</details>

![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)

<br>
<sup>Login Screen after running the hack</sup>
<br><br>

## Enable Staff Mode

<details>
<summary>Enables some hidden features and sets your client to staff mode</summary>
 
This will trick your client into thinking that you are Discord Staff (by modifiying the flags)
and also enables the secret experiments and Developer Options Menu (where you can get secret unrelesed discord updates, 
emulate a different client, generate build overrides etc.)
Credit for the Settings hack to https://gist.github.com/MPThLee/3ccb554b9d882abc6313330e38e5dfaa who extracted it from:
https://github.com/samogot/betterdiscord-plugins (The original Creator)

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().flags += 1;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().flags += 1}}}]);window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.isDeveloper !== undefined) {Object.defineProperty(m.default, "isDeveloper", {get: (a) => 1,set: (a) => a,configurable: true}); console.log("%cWorked!", "font-size: 50px");return console.log(`%cYou now have Developer Options and a Staff badge. You can find the Developer Settings in the Settings's bottom tab!`, "font-size: 16px")}if (m.isDeveloper !== undefined) {Object.defineProperty(m, "isDeveloper", {get: (a) => 1,set: (a) => a,configurable: true}); console.log("%cWorked!", "font-size: 50px");return console.log(`%cYou now have Developer Options and a Staff badge. You can find the Developer Settings in the Settings's bottom tab!`, "font-size: 16px")}}}]);
```

</details>

![discorddevoptions](https://user-images.githubusercontent.com/55095883/116668009-29223780-a99d-11eb-9387-625f10c64196.png)

<sup>Developer Options Setting</sup>
<br>

## Get all Badges

<details>
  <summary>This script enables all Badges on you client.</summary>

Note that other users won't see the badge<br>

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().flags = -1;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().flags = -1}}}]);window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().public_flags += 1;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().public_flags += 1}}}]);
```

</details>

![preview](https://user-images.githubusercontent.com/55095883/110086787-191e1b00-7d93-11eb-8f0f-2b3a76210155.png)

<br>
<sup>This isn't a fake screenshot your client will really display this.</sup>
<br><br>

## Easy Edit mode

<details>
<summary>you can use this to make Fake Screenshots without having to do Inspect Element each time</summary>

```js
document.designMode = 'on'
```

</details>
<br>

## Free Discord Nitro (hack)

<details>
  <summary>Get some Nitro features without buying Nitro</summary>
 
Tricks your client into thinking you have Nitro. Converts the API request into non-nitro requests, so Discord won't notice that yoou don't have Nitro.
Be extra careful with scripts that claim to do this, this script is the only working one. If you find a copy of this script, not directly provided by me or this repo, pls report it to me, its probably a scam.<br>
Credit to https://github.com/An00nymushun/DiscordFreeEmojis for the Emoji handling part.<br>
Note that not every feature is supported as, some things that run Server Side can't be simulated.
But basic features (like animated emojis) should work.

```js
/*
I removed the code bc this shouldn't go public. Ppl would just copy and paste this anywhere and bad ppl would backdoor it.
Also I don't want Discord to fix this.

This script was replaced by Discord Oxygen.
*/
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116668188-5d95f380-a99d-11eb-96cf-a0e2dfc6bb23.png)

<sup>The Subscription Overview. The Account used for the Screenshot **didn't** buy Nitro</sup>
<br>

## View NSFW Channels

<details>
  <summary>Displays NSFW Channels On A below 18 account.</summary>
<br>
  
Only use this script if you are 18+!
```js
var findModule=(item)=>window.webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default[item]!==undefined)return m.default}}])
findModule('getCurrentUser').getCurrentUser().nsfwAllowed = true
```

</details>
  
![grafik](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/6zsLEjYET0.png)

<br>
<sup>Before Running The Script ^^</sup><bbr>
<br>
  
![grafik](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/ypzEY7Yw0u.png)

<br>
<sup>After Running The Script ^^</sup><bbr>
<br>
  


## Get hidden Channel ID's

<details>
  <summary>Displays the ID's of channel that you can't see without hacks.</summary>

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getPrivateChannelIds !== undefined) {return console.log(m.default.getPrivateChannelIds())}if (m.getPrivateChannelIds !== undefined) {return console.log(m.getPrivateChannelIds())}}}]);
```

</details>

![grafik](https://user-images.githubusercontent.com/55095883/116670257-cda57900-a99f-11eb-8f96-7d8d54754535.png)

<br>
<sup>Example Output of this command</sup><bbr>
<br>
  

## Changing Password

<details>
  <summary>Change the Password of the Account, thats currently logged in.</summary>

  

```js
  let oldpassword = "";
  let newpassword = "";

  window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {fetch("https://discord.com/api/v9/users/@me", { "credentials": "include", "body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\"}", "method": "PATCH", "headers": { "Authorization": m.default.getToken(), "Content-Type":"application/json" }}); return}if (m.getToken !== undefined) {fetch("https://discord.com/api/v9/users/@me", {"credentials": "include","body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\"}","method":"PATCH","headers": {"Authorization": m.getToken(), "Content-Type":"application/json"}});return}}}]);
```

</details>
  
  ## Add guild features
<details>
  <summary>Enable server features... Replace 'FEATURE' with something like 'PARTNERED' or 'VERIFIED'<br><img src="https://user-images.githubusercontent.com/55095883/121220849-4a702080-c885-11eb-965c-317749da0196.png"></img>

<img src="https://user-images.githubusercontent.com/55095883/121219947-7b9c2100-c884-11eb-99f1-e0a8525512a9.png"></img><img src="https://user-images.githubusercontent.com/55095883/121220469-e9484d00-c884-11eb-816f-2d3b9f46a585.png"></img>)
</summary>

Unknown Author.

```js
let serverid = "";
let feature = "";

window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getGuilds !== undefined) {return m.default.getGuild(serverid).features.add(feature)}if (m.getGuilds !== undefined) {return m.getGuild(serverid).features.add(feature)}}}]);
```

</details>

## Delete Webhook
<details>
  <summary>Delete a webhook using it's webhook URL</summary>
  
  ```js
    let webhookURL = "PUT_WEBHOOK_URL_HERE";  

    await fetch(webhookURL, {
      "method": "DELETE",
    });
  ```
</details>

## Phone, Email verification bypass

<details>
  <summary>Bypass Phone and email verification in server, this cannot let you send message but you still can connect and and talk in voice channels
</summary>


```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().phone = '+1234567890';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().phone = '+1234567890'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().email = 'email@email.com';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().email = 'email@email.com'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().verified = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().verified = true}}}]);
```

</details>

## Change Client Color

<details>
  <summary>Changes Your Client Color To Your Liking.<br><img src="https://cdn.discordapp.com/attachments/841333120870645760/858800547958882334/unknown.png"></img>
</summary>

Unknown Author.
```js
__SECRET_EMOTION__.injectGlobal(`
    * {
--background-primary: #000000;
    --background-secondary: #000000;
--background-secondary-alt: #070707ff;
--background-accent: #252525;
--background-floating: #242424ff;
    --scrollbar-thin-track: #000000;
    --channeltextarea-background: #151515;
    }
`)
```

</details>

</details>


# The Framework

<details>
  <summary>Click here</summary>
  
  Now in a seperate repo: https://github.com/hxr404/discord-oxygen
  
The Framework is a new project, wich combines every Console Hack into a single script.<br>
Simply Include the source code (.js file) into your Discord Client (Desktop or Web).<br>
You can either do this by pasting it into your Console (CTRL + SHIFT + I, CTRL + V, ENTER)<br>
Or by adding it as a Userscript. (You need a Browser Extension, for Firefox I recommend Firemonkey)<br>

## How it works

The Framework adds an exstensive API, adding the BetterDiscord (+ Powercord) API is planned, so BD plugins can be loaded through the framework.
Its similar to a modloader of a game, except for it is preconfigured and all good mods are already installed (Open a PR or issue if you want to merge your mods to mainstream)
Its modularized and each module runs seperatetly in its own Block Scope, not like the Old Nitro hack.
This should prevent Discord from fixing it, as it no longer depends on hardcoded modifications.

## Features:

<details>
  <summary>Screenhots will be added here</summary>
</details>
 

## History

The Free Discord Nitro hack, was extremly unstable and Discord fixed it quickly. Thats when I started working on the Framework. It was the improved Discord Nitro.
It is much more performant, offers better UX and made development way easier. After successfully merging the old Nitro hack, I continued improving Nitro with more features. And then I thought: why only adding default Nitro features? There are much more awesome features that can be useful as well. And since the Framwerork is modularized, it took about 5 Minutes merging the other Console hacks. And like this a new project was born.
  
  
</details>
