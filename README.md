Note: I'm not affilated with Discord and do not encourage using any of these hacks. Use everything here at your own risk. This is meant for educational purposes only and using these codeblocks may result in your account being disabled/terminated.

# Community
My main Server (hxr404) is **not** for anything related to these hacks. For anything violating the ToS (including talking about these hacks) you will get banned there.<br>
Join my alt Server instead: https://discord.gg/T7T3svK3rf (1st invite)<br>
Marcell D'Avis with the crown Icon is my official alt account. Anyone who does not have the crown Icon on the Server mentioned above is **not** me.
Please do not use console hacks of people impersonating me, you'll get scammed.<br>
I'll update this invite regularly, if my account gets compromised or Discord shuts down the Server, I will create a new "Marcell D'Avis",<br>a new Server and will then update the invite above.<br>
<sup>You can join my official Community Server (Invite in Expire-Bot Readme), wich is also the community for my YouTube channel and other ledgit things. Most people on that Server are joined because of these things and **not** because of "hacks", so please don't ask them about hacks.</sup>

# Inner workings of Discord
<details>
  <summary>Click here</summary>

## Discord Token Synatx
<details>
<table>
  <tr><th></th><th>Example</th></tr>
  <tr><td>User ID Encoded in Base64</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>Timestamp -epoch(1293840000) converted to base64 (credit to @Flam3rboy)</td><td>XCgboz</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>HMAC (credit to @Flam3rboy) consiting of 27 chars (uppercase/lowercase letters, numbers, - or _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
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

![grafik](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)<br>
<sup>How sending Audioo/Video Messages in Discord Works.</sup>
</details>
<br>
</details>
<br>

# Console Hacks
<details>
  <summary>Click here</summary>
  
## How to use these Hacks
It only works on Dekstop Versions (Windows, Linux, MacOS), not on Mobile
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is electronjs wich is basically google chrome)
2. Click on "Console" if not already selected
3. Paste the script in
4. Press enter


## Obtaining your Token
<details>
<summary>Copies your Token into the Clipboard.</summary>

paste this into the Console (while being logged in)
and before the loading animation has finished, paste it again.
```js
window.location.reload();
copy(document.body.appendChild(document.createElement `iframe`).contentWindow.window.localStorage.token);
```
The token should be in your Clipboard.
If it's just "null" or "undefined" do the same thing again. Don't wait to lomg inbetween the two times
</details>
<br>

## Logging in using Token
<details>
<summary>Modifies the Login screen so you can use Tokens to log in.</summary>

paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)
```js
function login(e){setInterval(()=>{document.body.appendChild(document.createElement`iframe`).contentWindow.localStorage.token=`"${e}"`},50),setTimeout(()=>{window.location.reload()},2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-_djjkz input-cIJ7To")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-AtZOdT button-3k0cO7 button-38aScr lookFilled-1Gx00P colorBrand-3pXr91 sizeLarge-1vSeWK fullWidth-1orjjo grow-q77ONN")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-32qID7")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-2KCXvj size14-e6ZScH h5-18_1nd title-3sZWYQ defaultMarginh5-2mL-bP")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-aR7y1d qrLogin-1AOZMt")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-3huAjp")[0]).parentElement.removeChild(element);
```
and log in<br>
Note that this doesn't work with Bot tokens, Bot tokens are different than user tokens, and Discord doesn't support this.<br>
</details>

![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)<br>
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
(()=>{const e="function"==typeof webpackJsonp?webpackJsonp([],{__extra_id__:(e,t,n)=>t.default=n},["__extra_id__"]).default:webpackJsonp.push([[],{__extra_id__:(e,t,n)=>e.exports=n},[["__extra_id__"]]]);delete e.m.__extra_id__,delete e.c.__extra_id__;Object.defineProperty(((t,n)=>((t,n={})=>{const{cacheOnly:l=!0}=n;for(let n in e.c)if(e.c.hasOwnProperty(n)){let l=e.c[n].exports;if(l&&l.__esModule&&l.default&&t(l.default))return l.default;if(l&&t(l))return l}if(l)return console.warn("Cannot find loaded module in cache"),null;console.warn("Cannot find loaded module in cache. Loading all modules may have unexpected side effects");for(let n=0;n<e.m.length;++n)try{let l=e(n);if(l&&l.__esModule&&l.default&&t(l.default))return l.default;if(l&&t(l))return l}catch(e){}return console.warn("Cannot find module"),null})(e=>t.every(t=>void 0!==e[t]),n))(["isDeveloper"]),"isDeveloper",{get:e=>1,set:e=>e,configurable:!0})})();
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void 0).exports.default.getCurrentUser().flags+=1
```
</details>

![discorddevoptions](https://user-images.githubusercontent.com/55095883/116668009-29223780-a99d-11eb-9387-625f10c64196.png)
<sup>Developer Options Setting</sup>
<br>


## Get all Badges
<details>
  <summary>This script enables all Badges on you client.</summary>

Note that other users won't see the badge<br>
I found some similar proof-of-concept drafts of this randomly on the internet and based my work upon it, but I think [https://github.com/X-x-X-0/discord-js](https://github.com/X-x-X-0/discord-js) could be the original author<br>
```js
const req = webpackJsonp.push([[], { extra_id: (module, exports, req) => (module.exports = req) }, [['extra_id']]]);
for (let i in req.c) {
  if (req.c.hasOwnProperty(i)) {
    let m = req.c[i].exports;
    if (m && m.__esModule && m.default && m.default.getCurrentUser) {
      m.default.getCurrentUser().flags |= 410575;
      break;
    }
  }
}

```
</details>

![preview](https://cdn.discordapp.com/attachments/852927271958347828/865720717143310346/Screenshot_2021-07-16_182251.png)<br>
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
Its a WIP, join the Server Linked in #Community if you want to know more.
If you are a developer and want to contribute, also DM me.
*/
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116668188-5d95f380-a99d-11eb-96cf-a0e2dfc6bb23.png)
<sup>The Subscription Overview. The Account used for the Screenshot **didn't** buy Nitro</sup>
<br>

## oauth Bot and System
<details>
  <summary>test. Doesn't work. Don't run this</summary>

```js
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().bot=true
```
```js
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().system=true
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116669184-908cb700-a99e-11eb-9a7f-62c0d19e5486.png)<br>
<sup>Using the System Badge to make funny fake announcements</sup><br>
![grafik](https://user-images.githubusercontent.com/55095883/116669793-47893280-a99f-11eb-972d-bcc8e07c65dd.png)<br>
<sup>Fake Bot badge</sup><br>
![grafik](https://user-images.githubusercontent.com/55095883/116669897-6982b500-a99f-11eb-8dfc-53caa1d312e3.png)<br>
<sup>User Pop-Out with Bot badge</sup><br>
<br>

## Get hidden Channel ID's
<details>
  <summary>Displays the ID's of channel that you can't see without hacks.</summary>

All credit to [https://github.com/X-x-X-0/discord-js](https://github.com/X-x-X-0/discord-js)
```js
Object.values(webpackJsonp.push([
    [], {
        ['']: (_, e, r) => {
            e.cache = r.c
        }
    },
    [
        ['']
    ]
]).cache).find(m => m.exports && m.exports.default && m.exports.default.getPrivateChannelIds !== void 0).exports.default.getPrivateChannelIds()
```
</details>

![grafik](https://user-images.githubusercontent.com/55095883/116670257-cda57900-a99f-11eb-8f96-7d8d54754535.png)<br>
<sup>Example Output of this command</sup><bbr>
<br>
  
## Changing Password
<details>
  <summary>Change the Password of the Account, thats currently logged in.</summary>

  ```js
  await fetch("https://discord.com/api/v9/users/@me", {
    "credentials": "include",
    "body": "{\"password\":\"oldpassword\",\"new_password\":\"hackedbyhxr404\"}",
    "method": "PATCH",
});
```
</details>
  
  ## Add guild features
<details>
  <summary>Enable server features... Replace 'FEATURE' with something like 'PARTNERED' or 'VERIFIED'<br><img src="https://user-images.githubusercontent.com/55095883/121220849-4a702080-c885-11eb-965c-317749da0196.png"></img>

<img src="https://user-images.githubusercontent.com/55095883/121219947-7b9c2100-c884-11eb-99f1-e0a8525512a9.png"></img><img src="https://user-images.githubusercontent.com/55095883/121220469-e9484d00-c884-11eb-816f-2d3b9f46a585.png"></img>)
</summary>

Unknown Author.
```js
Object.values(webpackJsonp.push([[],{['']:(_,e,r)=>{e.cache=r.c}},[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getGuilds!==void 0).exports.default.getGuild('SERVERID').features.add('FEATURE')
```
</details>

## Change Client Color
<details>
  <summary>Changes Your Client Color To Your Likeing.<br><img src="https://cdn.discordapp.com/attachments/841333120870645760/858800547958882334/unknown.png"></img>
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
