# Discord-Console-hacks

Note: I'm not affilated with Discord in any way. Use everything here at your own risk.

## Inner workings of Discord

### Discord Token Synatx
<details>
<table>
  <tr><th></th><th>Example</th></tr>
  <tr><td>User ID Encoded in Base64</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>1 Uppercase letter, user specific</td><td>X</td></tr>
  <tr><td>2 chars (uppercase/lowercase letters, numbers, - or _), user specific</td><td>Cg</td></tr>
  <tr><td>3 chars (uppercase/lowercase letters, numbers, - or _), only user specific for bot accounts</td><td>boz</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>27 Random chars (uppercase/lowercase letters, numbers, - or _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
</table>
NTzQvPcLBacBmgajXQc7QAaU.XCgboz.c4t51kFWSEmdmaPnKoyUuu8E78E
</details>

<br>
<br>

## Console Hacks

### How to use these Hacks
It only works on Dekstop Versions (Windows, Linux, MacOS), not on Mobile
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is electronjs wich is basically google chrome)
2. Click on "Console" if not already selected
3. Paste the script in
4. Press enter


### Obtaining your Token
<details>
<summary>Copied your Token into the Clipboard.</summary>

paste this into the Console (while being logged in)
and before the loading animation has finished, paste it again.
```js
window.location.reload();
copy(document.body.appendChild(document.createElement `iframe`).contentWindow.window.localStorage.token);
```
The token should be in your Clipboard.
If it's just "null" or "undefined" do the same thing again. Don't wait to lomg inbetween the two times
</details>

### Logging in using Token
![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)
<sup>Login Screen after running the hack</sup>
<details>
<summary>Modifies the Login screen so you can use Tokens to log in.</summary>

paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)
```js
function login(e){setInterval(()=>{document.body.appendChild(document.createElement`iframe`).contentWindow.localStorage.token=`"${e}"`},50),setTimeout(()=>{window.location.reload()},2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-_djjkz input-cIJ7To")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-AtZOdT button-3k0cO7 button-38aScr lookFilled-1Gx00P colorBrand-3pXr91 sizeLarge-1vSeWK fullWidth-1orjjo grow-q77ONN")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-32qID7")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-2KCXvj size14-e6ZScH h5-18_1nd title-3sZWYQ defaultMarginh5-2mL-bP")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-aR7y1d qrLogin-1AOZMt")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-3huAjp")[0]).parentElement.removeChild(element);
```
and log in<br>
Note that this doesn't work with Bot tokens, Bot tokens are different than user tokens, and Discord doesn't support this.<br>
</details>

### Enable Staff Mode
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

### Get all Badges
![preview](https://user-images.githubusercontent.com/55095883/110086787-191e1b00-7d93-11eb-8f0f-2b3a76210155.png)<br>
<sup>This isn't a fake screenshot your client will really display this.</sup>
<details>
  <summary>This script enables all Badges on you client.</summary>

Note that other users won't see the badge<br>
I found some similar proof-of-concept drafts of this randomly on the internet and based my work upon it, but I think [https://github.com/X-x-X-0/discord-js](https://github.com/X-x-X-0/discord-js) could be the original author<br>
```js
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().flags=-1
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().public_flags=-1
```
</details>

### Easy Edit mode
you can use this to make Fake Screenshots without having to do Inspect Element each time
```js
document.designMode = 'on'
```

### Free Discord Nitro (hack)
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
Its a WIP, DM me if you want to know more.
If you are a developer and want to contribute, also DM me.
*/
```
</details>

### oauth Bot and System
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
<details>

### Get hidden Channel ID's
<details>
  <summary>Displays the ID's of channel that you can't see without hacks.</summar>

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
