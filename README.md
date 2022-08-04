**Note:** I'm not affilated with Discord and do not encourage using any of these hacks. Use everything here at your own risk. This is meant for **educational purposes only** and using these codeblocks may result in your account being disabled/terminated.

# Community

<details>
  <summary>We're switching to Matrix!</summary>
  
Matrix is a community-based, decentralized, privacy friendly, end-to-end encrypted (super secure), uncensorable and open source messaging protocol, which unlike discord promotes custom clients and modifications. There are multiple different clients available, the most popular one (and also the refrence implementation) is Element. It runs on every OS and even has a pretty good web version. For more information check out https://matrix.org and https://element.io.<br>
I often get asked: "*If Matrix/Element is so super awesome, why didn't you start using earlier?*"<br>
Well actually I've been using Matrix for quite a long time now, Anonymous already switched to it many years ago. For me Matrix always has been something serious, I never really thought about using it for this Discord stuff.
</details>

Here's the invite to the community: https://matrix.to/#/#discord-oxygen:matrix.org

The main community is on matrix, most channels are encrypted and can only be accessed from within matrix.
For those of you who can't use Matrix we created the Discord Server, its bridged to the community (=every message you send in Discord automatically appears in matrix and vice-versa)<br>
Here's the invite link: https://discord.gg/m8jbrkzExz (4th server)<br>


Please don't use console hacks not sent by me, or you might risk losing your account.<br>
I'll update this invite regularly, if e.g. my account gets compromised or Discord shuts down the server, I will create a new account, a new server and then will update the invite above.<br>
If the invite doesn't work anymore, it means the server got deleted and you need to wait until I can create a new account.

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
Check out this article about Reverse Engineering Discord, and the proof that Discord decrypts your encrypted data: <a href="https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626">https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626</a><br>
They can also read your messages (e.g. in DM's), log all edits and deleted messages and record your voice calls.

![grafik](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)

<br>
<sup>How sending Audio/Video Messages in Discord Works.</sup>
</details>
<br>
</details>
<br>

# Console Hacks

<details>
  <summary>Click Here</summary>
  

## Be Careful!

As stated in my disclaimer, I don't promote using any kind of client modifications. Please don't use the code found here for illegal / hacking purposes, or you might risk seeing this error message:<br>

![image](https://user-images.githubusercontent.com/55095883/134189043-4da003de-4829-4d60-888a-6014ebb5c2b8.png)

  

## How to use these Hacks

It only works on Desktop Versions (Windows, Linux, MacOS), not on Mobile.
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is electronjs wich is basically google chrome)
2. Click on "Console" if not already selected
3. Paste the script in
4. Press enter

## Obtaining your Token

<details>
<summary>Copies your Token into the clipboard.</summary>

Paste this into the Console (while being logged in)

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {return copy(m.default.getToken())}if (m.getToken !== undefined) {return copy(m.getToken())}}}]); console.log("%cWorked!", "font-size: 50px"); console.log(`%cYou now have your token in the clipboard!`, "font-size: 16px")
```

The token should be in your clipboard now.
</details>
<br>

## Logging in using Token

<details>
<summary>Modifies the login screen so you can use tokens to log in.</summary>

Paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)

```js
function login(e) {setInterval(() => {window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.setToken !== undefined) {return m.default.setToken(e)}if (m.setToken !== undefined) {return m.setToken(e)}}}]);console.log("%cWorked!", "font-size: 50px");}, 50), setTimeout(() => {window.location.reload()}, 2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-3FGxgL input-2g-os5")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-emkd0_ button-1cRKG6 button-f2h6uQ lookFilled-yCfaCM colorBrand-I6CyqQ sizeLarge-3mScP9 fullWidth-fJIsjq grow-2sR_-F")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-315RVT")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-21JIj7 size14-3fJ-ot h5-2RwDNl title-3hptVQ defaultMarginh5-3Jxf6f")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-bPT0qU qrLogin-1ejtpI")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-2r9gHa")[0]).parentElement.removeChild(element);
```

and log in<br>
Note that this doesn't work with bot tokens. Bot tokens are different than user tokens, and Discord doesn't support this.<br>
</details>

![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)

<br>
<sup>Login Screen after running the hack</sup>
<br><br>

## Enable Staff Mode

<details>
<summary>Enables some hidden features and sets your client to staff mode</summary>
 
This will trick your client into thinking that you are a Discord Staff (by modifiying the flags)
and also enables the secret experiments and Developer Options Menu (where you can get secret unreleased discord updates, 
emulate a different client, generate build overrides etc.)
Credit for the Settings hack to https://gist.github.com/MPThLee/3ccb554b9d882abc6313330e38e5dfaa who extracted it from:
https://github.com/samogot/betterdiscord-plugins (The original creator)

```js
const c = window.webpackChunkdiscord_app.push([[ Symbol() ], {}, ({ c }) => Object.values(c)]);
userMod = c.find(x => x?.exports?.default?.getUsers).exports.default.__proto__;
nodes = Object.values((c.find(x => typeof x?.exports?.default?.isDeveloper !== "undefined")).exports.default._dispatcher._dependencyGraph.nodes);
nodes.find(x => x.name === "ExperimentStore").actionHandler["CONNECTION_OPEN"]({ user: { flags: 1 }, type: "CONNECTION_OPEN", experiments: [] });
oldGCUser = userMod.getCurrentUser;
userMod.getCurrentUser = () => { return { hasFlag: () => true }};
nodes.find(x => x.name === "DeveloperExperimentStore").actionHandler["CONNECTION_OPEN"]();
userMod.getCurrentUser = oldGCUser;
// Thanks to 257109471589957632
```

</details>

![discorddevoptions](https://cdn.discordapp.com/attachments/788198099067076638/1004823296489029702/unknown.png)

<sup>Developer Options Setting</sup>
<br>

## Get all Badges

<details>
  <summary>This script enables all badges on your client.</summary>

Note that other users won't see the badge, only you can.<br>

```js
webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default.getCurrentUser!==undefined){return m.default.getCurrentUser().flags=99999999999}}}]);
```
to get all badges and place your account under quarantine (visually):
```js
webpackChunkdiscord_app.push([[Math.random()],{},(req)=>{for(const m of Object.keys(req.c).map((x)=>req.c[x].exports).filter((x)=>x)){if(m.default&&m.default.getCurrentUser!==undefined){return m.default.getCurrentUser().flags=-1}}}]);
```

</details>

![preview](https://user-images.githubusercontent.com/55095883/110086787-191e1b00-7d93-11eb-8f0f-2b3a76210155.png)

![preview](https://cdn.discordapp.com/attachments/788198099067076638/1004823731056676954/unknown.png)

<br>
<sup>This isn't a fake screenshot, your client will really display this.</sup>
<br><br>

## Bot and System Tag
<details>
  <summary>Spoof that you're a bot or the system</summary>

Bot tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().bot = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().bot = true}}}])
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isVerifiedBot = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isVerifiedBot = () => true}}}])
```
System tag code:
```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().isSystemUser = () => true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().isSystemUser = () => true}}}])
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116669184-908cb700-a99e-11eb-9a7f-62c0d19e5486.png)<br>
<sup>Using the System Badge to make funny fake announcements</sup><br>
![grafik](https://user-images.githubusercontent.com/55095883/116669793-47893280-a99f-11eb-972d-bcc8e07c65dd.png)<br>
<sup>Fake Bot badge</sup><br>
![grafik](https://user-images.githubusercontent.com/55095883/116669897-6982b500-a99f-11eb-8dfc-53caa1d312e3.png)<br>
<sup>User Pop-Out with Bot badge</sup><br>
<br>
  
## Easy Edit mode

<details>
<summary>You can use this to make fake screenshots without having to do Inspect Element (CTRL + SHIFT + I) each time</summary>

```js
document.designMode = 'on'
```

</details>
<br>

## Free Discord Nitro (hack)

<details>
  <summary>Get some Nitro features without having to buy Nitro</summary>
 
Tricks your client into thinking you have Nitro. Converts the API request into non-nitro requests, so Discord won't notice that you don't have Nitro.
Be extra careful with scripts that claim to do this, this script is the only working one. If you find a copy of this script not directly provided by me or this repo, please report it to me, its probably a scam.<br>
Credit to https://github.com/An00nymushun/DiscordFreeEmojis for the emoji handling part.<br>
Note that not every feature is supported as some things that run server side can't be simulated.
But basic features (like animated emojis) should work.

```js
/*
I removed the code because this shouldn't go public. People would just copy and paste this anywhere and bad people would backdoor it.
Also I don't want Discord to fix this.

This script was replaced by Discord Oxygen (https://github.com/hxr404/Discord-Oxygen).
*/
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116668188-5d95f380-a99d-11eb-96cf-a0e2dfc6bb23.png)

<sup>The Subscription Overview. The account used for the screenshot **didn't** buy Nitro</sup>
<br>

## View NSFW Channels

<details>
  <summary>Displays NSFW channels on an under-18 account.</summary>
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
  <summary>Displays the ID's of channel that you can't see without client modifications.</summary>

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
  <summary>Changes the password of the account thats currently logged in.</summary>

  

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
  <summary>Bypass phone and email verification in server, this cannot let you send messages but you can connect and and talk in voice channels.
</summary>


```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().phone = '+1234567890';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().phone = '+1234567890'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().email = 'email@email.com';}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().email = 'email@email.com'}}}]);
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getCurrentUser !== undefined) {return m.default.getCurrentUser().verified = true;}if (m.getCurrentUser !== undefined) {return m.getCurrentUser().verified = true}}}]);
```

</details>

## Discord Activities

<details>
  <summary>Added an activity button in voice channel
</summary>


```js
var AppIds = ["755600276941176913", "880218394199220334", "755827207812677713", "773336526917861400", "814288819477020702", "832012774040141894", "879864070101172255", "879863881349087252", "832012854282158180", "878067389634314250", "902271654783242291", "879863686565621790", "879863976006127627", "852509694341283871", "832013003968348200", "832025144389533716", "763133495793942528", "880218832743055411", "878067427668275241", "879864010126786570", "879864104980979792", "891001866073296967", "832012586023256104", "832012682520428625", "832013108234289153", "763116274876022855", "832012730599735326", "832012938398400562", "832025061657280566", "801133024841957428", "832012815819604009", "832012894068801636", "832025114077298718", "832025993019260929"]
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getEnabledAppIds !== undefined) {return m.default.getEnabledAppIds = () => AppIds}}}]);
```

<img src="https://i.ibb.co/rmskPSH/image.png"></img>
</details>

## Change Client Color

<details>
  <summary>Changes your client color to your liking.<br><img src="https://cdn.discordapp.com/attachments/841333120870645760/858800547958882334/unknown.png"></img>
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
  
The Framework is a new project, wich combines every console hack into a single script.<br>
Simply include the source code (.js file) into your Discord client (Desktop or Web).<br>
You can either do this by pasting it into your console (CTRL + SHIFT + I, CTRL + V, ENTER)<br>
Or by adding it as a userscript. (You need a browser extension, for Firefox I recommend Firemonkey)<br>

## How it works

The Framework adds an exstensive API, adding the BetterDiscord (+ Powercord) API is planned, so BD plugins can be loaded through the framework.
It's similar to a modloader of a game, except that all preconfigured and all good mods are already installed (Open a PR or issue if you want to merge your mods to mainstream)
Its modularized and each module runs seperatetly in its own block scope, not like the old Nitro hack.
This should prevent Discord from fixing it, as it no longer depends on hardcoded modifications.

## Features:

<details>
  <summary>Screenhots will be added here</summary>
</details>
 

## History

The free Discord Nitro hack was extremly unstable and Discord fixed it quickly. That's when I started working on the framework. It was the improved Discord Nitro.
It is much more performant, offering better UX and made development way easier. After successfully merging the old Nitro hack, I continued improving Nitro with more features. And then I thought: why only add default Nitro features? There are so much more awesome features that could be useful as well. Since the framwerork is modularized, it took about 5 minutes merging the other console hacks. And like this a new project was born.
  
  
</details>
