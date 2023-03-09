# Discord Console Hacks
[![License: GPL v3+](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

:warning: **Note:** I'm not affiliated with Discord and do not encourage using any of these scripts. Use everything here at your own risk. This is meant for **educational purposes only** and using these codeblocks may result in your account being disabled/terminated.

***


## Community

<details>
<summary>Join us on Matrix!</summary>
  
Matrix is a community-based, decentralized, privacy friendly, end-to-end encrypted (super secure), uncensorable and open source messaging protocol, which, unlike Discord, promotes custom clients and modifications. There are multiple different clients available, the most popular one (and also the reference implementation) is Element. It runs on most operating systems and also has a pretty good web version. For more information, check out https://matrix.org and https://element.io.<br>
I often get asked: "*If Matrix is so super awesome, why didn't you start using it earlier?*"<br>
Well actually I've been using Matrix for quite a long time now. I never really thought about using it for this Discord stuff.
</details>

Here's the invite to the community: https://matrix.to/#/#discord-oxygen:matrix.org

The main community is on Matrix, most channels are encrypted and can only be accessed from within Matrix.
For those of you who can't use Matrix, we've created a Discord server. It's bridged to the community. (Every message you send in Discord automatically appears in Matrix and vice-versa.)<br>
Here's the invite link: https://discord.gg/m8jbrkzExz (4th server)<br>


Please don't use console hacks not sent by me, or you might risk losing your account.<br>
I'll update this invite regularly, if for example my account gets compromised or Discord shuts down the server. If something like that occurs, I will create a new account, a new server and then update the invite above.<br>
If the invite doesn't work anymore, it means the server got deleted and you need to wait until I can create a new account.

***

## Inner workings of Discord

**Disclaimer:** The information provided in this section is obtained through reverse engineering and NOT verified for it's accuracy. Therefore it might be outdated as well.

<details>
<summary>Expand</summary>

<br>

***


### Discord Token Syntax

<details>
<summary>Expand</summary>

<table>
  <tr><th></th><th>Example</th></tr>
  <tr><td>User ID Encoded in Base64</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>Timestamp -epoch(1293840000) converted to base64</td><td>XCgboz</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>HMAC consiting of 27 chars (uppercase/lowercase letters, numbers, - or _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
</table>
There is this awesome diagram from <a href="https://github.com/hxr404/Discord-Console-hacks/issues/2">#2</a> which shows the exact token structure:<br><br>
<img src="https://user-images.githubusercontent.com/34555296/120932740-4ca47480-c6f7-11eb-9270-6fb3fbbd856c.png"></img> <br>
</details>
<br>


### Discord's Internal Server Structure

<details>
<summary>Expand</summary>

Check out this article about reverse engineering Discord, and the proof that Discord decrypts your encrypted data: <a href="https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626">https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626</a><br>
They can also read your messages (e.g. in DM's), log all edits and deleted messages and record your voice calls.

![grafik](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)

<br>
<sup>How sending audio/video messages in Discord works.</sup>
</details>
<br>
</details>
<br>


## Console Hacks

As stated in my disclaimer, I don't promote using any kind of client modifications. Please don't use the code found here for illegal / hacking purposes, or you might risk seeing this error message:

![image](https://user-images.githubusercontent.com/55095883/134189043-4da003de-4829-4d60-888a-6014ebb5c2b8.png)

<details>
<summary>Expand</summary>

## How to use these Hacks

It only works on web and desktop versions (Windows, Linux, MacOS), not on mobile.
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is based on Electron, which is basically Google Chrome)
2. Click on "Console" if not already selected
3. Paste the script in the command field
4. Press enter

<br>


### Obtain your Token

Copies your Token into the clipboard.<br>
**:warning: DO NOT GIVE THIS TO ANYONE. It grants full access to your account.**

<details>
<summary>Expand</summary>

Paste this into the console (while being logged in):

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {return copy(m.default.getToken())}if (m.getToken !== undefined) {return copy(m.getToken())}}}]); console.log("%cDone!", "font-size: 50px"); console.log(`%cYou now have your token in the clipboard!`, "font-size: 16px")
```

The token should be in your clipboard now.<br>
Please be careful when pasting the token, sending it to someone is like giving away your address, keys and passport/ID.<br>
Someone who knows your token can impersonate you, mess with your friends and servers, spend your money (if you added a payment method for nitro), and even figure out your IP-Adress (aka. probably your real-life home adress) using the new devices feature.

</details>
<br>


### Log in using a Token

Modifies the login screen so you can use a token to log in.

<details>
<summary>Expand</summary>

Paste this into the console (CTRL + SHIFT + I) on the login screen (you need to be logged out):

```js
function login(e) {setInterval(() => {window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.setToken !== undefined) {return m.default.setToken(e)}if (m.setToken !== undefined) {return m.setToken(e)}}}]);console.log("%cWorked!", "font-size: 50px");}, 50), setTimeout(() => {window.location.reload()}, 2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-3FGxgL input-2g-os5")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-emkd0_ button-1cRKG6 button-f2h6uQ lookFilled-yCfaCM colorBrand-I6CyqQ sizeLarge-3mScP9 fullWidth-fJIsjq grow-2sR_-F")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-315RVT")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-21JIj7 size14-3fJ-ot h5-2RwDNl title-3hptVQ defaultMarginh5-3Jxf6f")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-bPT0qU qrLogin-1ejtpI")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-2r9gHa")[0]).parentElement.removeChild(element);
```

You can now log in using a token.<br>
Note that this doesn't work with bot tokens. Bot tokens are different from user tokens, and Discord doesn't support this.<br>

![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)<br>
<sup>Login Screen after running the script:</sup>
</details>
<br>


### Enable Staff Mode

Enables some hidden features and sets your client to staff mode.

<details>
<summary>Expand</summary>
 
This will trick your client into thinking that you are a staff member of Discord (by modifiying certain flags) and will also allow you to access the experiments tab, developer options, and more. (In these menus you can get unreleased Discord updates, emulate a different client, generate build overrides and more.)

```js
let wpRequire;
window.webpackChunkdiscord_app.push([[ Math.random() ], {}, (req) => { wpRequire = req; }]);
mod = Object.values(wpRequire.c).find(x => typeof x?.exports?.Z?.isDeveloper !== "undefined");
usermod = Object.values(wpRequire.c).find(x => x?.exports?.default?.getUsers)
nodes = Object.values(mod.exports.Z._dispatcher._actionHandlers._dependencyGraph.nodes)
try {
    nodes.find(x => x.name == "ExperimentStore").actionHandler["OVERLAY_INITIALIZE"]({user: {flags: 1}})
} catch (e) {}
oldGetUser = usermod.exports.default.__proto__.getCurrentUser;
usermod.exports.default.__proto__.getCurrentUser = () => ({isStaff: () => true})
nodes.find(x => x.name == "DeveloperExperimentStore").actionHandler["CONNECTION_OPEN"]()
usermod.exports.default.__proto__.getCurrentUser = oldGetUser
```
<br>

![discorddevoptions](https://cdn.discordapp.com/attachments/788198099067076638/1004823296489029702/unknown.png)<br>
<sup>Developer Options menu</sup>
</details>
<br>


### Get all Badges

This script gives you all badges locally, meaning that only you can see them.

<details>
<summary>Expand</summary>

Some badges grant access to specific options or menus.<br>

```js
(() => {
    let flags = {
        "DISCORD_EMPLOYEE": 1 << 0,
        "DISCORD_PARTNER": 1 << 1,
        "HYPESQUAD_EVENTS": 1 << 2,
        "BUG_HUNTER_LEVEL_1": 1 << 3,
        "HOUSE_BRAVERY": 1 << 6,
        "HOUSE_BRILLIANCE": 1 << 7,
        "HOUSE_BALANCE": 1 << 8,
        "EARLY_SUPPORTER": 1 << 9,
        "BUG_HUNTER_LEVEL_2": 1 << 14,
        "VERIFIED_BOT_DEVELOPER": 1 << 17,
        "CERTIFIED_MODERATOR": 1 << 18,
        "ACTIVE_DEVELOPER": 1 << 22
    };
    
    webpackChunkdiscord_app.push([[Math.random()], {}, req => {
        for (const m of Object.keys(req.c).map(x => req.c[x].exports).filter(x => x)) {
            if (m.default && m.default.getCurrentUser !== undefined) {
                return m.default.getCurrentUser().flags = Object.values(flags).reduce((pre, cur) => pre + cur, 0);
            }
        }
    }]);
})();
```
To get all badges and place your account under quarantine (visually):
```js
webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default.getCurrentUser!==undefined){return m.default.getCurrentUser().flags=-1}}}]);
```
<br>

![preview](https://user-images.githubusercontent.com/55095883/110086787-191e1b00-7d93-11eb-8f0f-2b3a76210155.png)<br>
<sup>This isn't a fake screenshot. Your client will really display this.</sup>

![preview](https://cdn.discordapp.com/attachments/788198099067076638/1004823731056676954/unknown.png)
</details>
<br>


### Bot & System Tag

Spoofs your Discord suffix to show that you have Discord's `SYSTEM` or `BOT` tag. (Only visible to you.)

<details>
<summary>Expand</summary>

Bot tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().bot = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().bot = true}}}])
```
  
Verified Bot tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().bot = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().bot = true}}}])
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isVerifiedBot = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isVerifiedBot = () => true}}}])
```
  
System tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isSystemUser = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isSystemUser = () => true}}}])
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116669184-908cb700-a99e-11eb-9a7f-62c0d19e5486.png)<br>
<sup>Using the System badge to make funny fake announcements</sup><br>

![grafik](https://user-images.githubusercontent.com/55095883/116669793-47893280-a99f-11eb-972d-bcc8e07c65dd.png)<br>
<sup>Fake Bot badge</sup><br>

![grafik](https://user-images.githubusercontent.com/55095883/116669897-6982b500-a99f-11eb-8dfc-53caa1d312e3.png)<br>
<sup>User pop-out with Bot badge</sup>
</details>
<br>


### Easy Edit Mode

You can use this to make fake screenshots without having to use Inspect Element (CTRL + SHIFT + I) each time.

<details>
<summary>Expand</summary>

```js
document.designMode = 'on'
```

</details>
<br>


### Spotify "Listen Along" Spoofer

Makes it possible to use the "Listen Along" feature without needing Spotify Premium.

<details>
<summary>Expand</summary>

```js
(webpackChunkdiscord_app.push([[''],{},e=>{m=[];for(let c in e.c)m.push(e.c[c])}]),m).find(m => m?.exports?.Z?.getAccounts).exports.Z.getAccounts().forEach((conn) => conn.type === "spotify" && (webpackChunkdiscord_app.push([[''],{},e=>{m=[];for(let c in e.c)m.push(e.c[c])}]),m).find(m => m?.exports?.Z?.isDispatching).exports.Z.dispatch({type: "SPOTIFY_PROFILE_UPDATE", accountId: conn.id, isPremium: true}))
```
</details>
<br>


### Free Discord Nitro

Makes it possible to use some of the features from Nitro without having to buy Nitro.<br>
This is **discontinued** and patched. Superseded by [Discord Oxygen](https://github.com/hxr404/Discord-Oxygen).

<details>
<summary>Expand</summary>
 
Tricks your client into thinking you have Nitro. Converts the API request into non-Nitro requests, so Discord won't notice that you don't have Nitro.<br>
Be extra careful with scripts that claim to do this, this script is the only working one. If you find a copy of this script not directly provided by me or this repository, please report it to me (it's probably a scam).<br>
Credit to https://github.com/An00nymushun/DiscordFreeEmojis for the emoji handling part.<br>
Note that not every feature is supported as some things that run server-side can't be simulated.
Basic features (like animated emojis) should work.

```js
/*
I removed the code because this shouldn't go public. People would just copy and paste this anywhere and bad people would backdoor it.<br>
Also I don't want Discord to fix this.<br>

This script was replaced by Discord Oxygen (https://github.com/hxr404/Discord-Oxygen).
*/
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116668188-5d95f380-a99d-11eb-96cf-a0e2dfc6bb23.png)<br>
<sup>The Subscription Overview page. The account used for the screenshot **didn't** buy Nitro.</sup>
</details>
<br>


### Enter NSFW Channels

Grants access to channels marked as NSFW on an under-18 account.<br>
**Only use this script if you are 18+! There is a reason those channels are marked as NSFW.**

<details>
<summary>Expand</summary>

This script is intended for people (>18) whose accounts have been wrongfully marked as underage. Don't use it for other purposes.

```js
var findModule=(item)=>window.webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default[item]!==undefined)return m.default}}])
findModule('getCurrentUser').getCurrentUser().nsfwAllowed = true
```
<br>

![grafik](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/6zsLEjYET0.png)<br>
<sup>Before running the script</sup><br>
<br>
  
![grafik](https://raw.githubusercontent.com/PndaBoi/pndaboi/main/ypzEY7Yw0u.png)<br>
<sup>After running the script</sup>
</details>
<br>


### Get Hidden Channel IDs

Displays the ID's of channels that you can't see without client modifications.

<details>
<summary>Expand</summary>

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getPrivateChannelIds !== undefined) {return console.log(m.default.getPrivateChannelIds())}if (m.getPrivateChannelIds !== undefined) {return console.log(m.getPrivateChannelIds())}}}]);
```
<br>

![grafik](https://user-images.githubusercontent.com/55095883/116670257-cda57900-a99f-11eb-8f96-7d8d54754535.png)<br>
<sup>Example output of this command</sup>
</details>
<br>


### Change Password

Changes the password of the account that is currently logged in.<br>
**Only use this on your own account! Stealing accounts is a crime in most countries.**

<details>
<summary>Expand</summary>

```js
let oldpassword = "";
let newpassword = "";

window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {fetch("https://discord.com/api/v9/users/@me", { "credentials": "include", "body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\"}", "method": "PATCH", "headers": { "Authorization": m.default.getToken(), "Content-Type":"application/json" }}); return}if (m.getToken !== undefined) {fetch("https://discord.com/api/v9/users/@me", {"credentials": "include","body": "{\"password\":\"" + oldpassword + "\",\"new_password\":\"" + newpassword + "\"}","method":"PATCH","headers": {"Authorization": m.getToken(), "Content-Type":"application/json"}});return}}}]);
```

</details>
<br>


### Add Guild Features

Enables server features (like having a partnered / verified server, or some boost-only features) locally, meaning everything is purely visual.

<details>
<summary>Expand</summary>

<img src="https://user-images.githubusercontent.com/55095883/121220849-4a702080-c885-11eb-965c-317749da0196.png"></img>
<img src="https://user-images.githubusercontent.com/55095883/121219947-7b9c2100-c884-11eb-99f1-e0a8525512a9.png"></img>
<img src="https://user-images.githubusercontent.com/55095883/121220469-e9484d00-c884-11eb-816f-2d3b9f46a585.png"></img>

Valid features are `PARTNERED` and `VERIFIED`.

```js
let serverid = "";
let feature = "";

window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getGuilds !== undefined) {return m.default.getGuild(serverid).features.add(feature)}if (m.getGuilds !== undefined) {return m.getGuild(serverid).features.add(feature)}}}]);
```

</details>
<br>


### Delete Webhook

Deletes a webhook using it's webhook URL.<br>
You could use this to delete the webhook of some scammers trying to token-grab you. :)

<details>
<summary>Expand</summary>

```js
let webhookURL = "PUT_WEBHOOK_URL_HERE";

await fetch(webhookURL, {
  "method": "DELETE",
});
```

</details>
<br>


### E-mail Address & Phone Number Verification Bypass

Bypasses e-mail address and phone number verification in servers. This does not let you send messages, but you can connect and talk in voice channels.

<details>
<summary>Expand</summary>


```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().phone = '+1234567890';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().phone = '+1234567890'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().email = 'email@email.com';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().email = 'email@email.com'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().verified = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().verified = true}}}]);
```

</details>
<br>


### Discord Activities

Adds the Activities button in the voice channel you're in.

<details>
<summary>Expand</summary>

```js
var AppIds = ["755600276941176913", "880218394199220334", "755827207812677713", "773336526917861400", "814288819477020702", "832012774040141894", "879864070101172255", "879863881349087252", "832012854282158180", "878067389634314250", "902271654783242291", "879863686565621790", "879863976006127627", "852509694341283871", "832013003968348200", "832025144389533716", "763133495793942528", "880218832743055411", "878067427668275241", "879864010126786570", "879864104980979792", "891001866073296967", "832012586023256104", "832012682520428625", "832013108234289153", "763116274876022855", "832012730599735326", "832012938398400562", "832025061657280566", "801133024841957428", "832012815819604009", "832012894068801636", "832025114077298718", "832025993019260929"]
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getEnabledAppIds !== undefined) {return m.default.getEnabledAppIds = () => AppIds}}}]);
```

<img src="https://i.ibb.co/rmskPSH/image.png"></img>
</details>
<br>


### Change Client Color

Changes your client's color to your liking.

<details>
<summary>Expand</summary>

<br><img src="https://cdn.discordapp.com/attachments/841333120870645760/858800547958882334/unknown.png"></img>
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
<br>


### AMOLED Theme on Desktop & Web

Activates the AMOLED theme from mobile on desktop and web, which uses darker colors than the normal theme and is better on the eyes.

<details>
<summary>Expand</summary>

```js
document.body.classList.add("theme-amoled");
```

</details>

</details>
<br>

***

## The Framework

Now in a seperate repository: https://github.com/Discord-Oxygen/Discord-Oxygen

<details>
<summary>Expand</summary>

The Framework is a new project, wich combines every console hack into a single script.<br>
Simply include the source code (.js file) into your Discord client (Desktop or Web).<br>
You can either do this by pasting it into your console (CTRL + SHIFT + I, CTRL + V, ENTER)<br>
Or by adding it as a userscript. (You need a browser extension, for Firefox I recommend Firemonkey)<br>

### How it works

The Framework adds an extensive API, adding the BetterDiscord (+ Powercord) API is planned, so BD plugins can be loaded through the framework.<br>
It's similar to a mod loader of a game, except that all good mods are already installed and pre-configured. (Open a pull request or issue if you want to merge your mods to mainstream.)<br>
The Framework is modularized and each module runs seperately in its own block scope, not like the old Nitro hack.
This should prevent Discord from fixing it, as it no longer depends on hardcoded modifications.

***


### History

The free Discord Nitro hack was extremely unstable and Discord fixed it quickly. That's when I started working on The Framework. It was the improved Discord Nitro.
It is much more performant, offering better UX and made development way easier. After successfully merging the old Nitro hack, I continued improving Nitro with more features. And then I thought: why only add default Nitro features? There are so much more awesome features that could be useful as well. Since The Framwerork is modularized, it took about 5 minutes merging the other console hacks. This is how a new project was born.

</details>

***

## License
    Copyright (C) 2022  hxr404

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
