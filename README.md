# Discord-Console-hacks

## Discord Token Synatx
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

## Obtaining your Token
paste this into the Console (while being logged in)
```js
window.location.reload();
copy(document.body.appendChild(document.createElement `iframe`).contentWindow.localStorage.token);
```
and the token should be in your Clipboard.
If it's "null" do the same thing again. It usually should work always at the 2nd time

## Logging in using Token
paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)
```js
function login(e){setInterval(()=>{document.body.appendChild(document.createElement`iframe`).contentWindow.localStorage.token=`"${e}"`},50),setTimeout(()=>{window.location.reload()},2500)}function buttonlogin(){login(document.getElementsByClassName("inputDefault-_djjkz input-cIJ7To")[0].value)}var element;(element=document.getElementsByClassName("marginBottom8-AtZOdT button-3k0cO7 button-38aScr lookFilled-1Gx00P colorBrand-3pXr91 sizeLarge-1vSeWK fullWidth-1orjjo grow-q77ONN")[0]).addEventListener("click",buttonlogin),(element=document.getElementsByClassName("marginBottom20-32qID7")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("colorStandard-2KCXvj size14-e6ZScH h5-18_1nd title-3sZWYQ defaultMarginh5-2mL-bP")[0]).innerHTML="Token",element.id="Token",(element=document.getElementsByClassName("transitionGroup-aR7y1d qrLogin-1AOZMt")[0]).parentElement.removeChild(element),(element=document.getElementsByClassName("verticalSeparator-3huAjp")[0]).parentElement.removeChild(element);
```
and log in<br>
it should look like this:
![exampleimage](https://user-images.githubusercontent.com/55095883/105732516-d0bc4380-5f30-11eb-959f-9fae0ddc9b7b.png)

## Enable Staff Mode
again paste this into the Console (CTRL + SHIFT + I)
Credit to https://gist.github.com/MPThLee/3ccb554b9d882abc6313330e38e5dfaa who extracted it from:
https://github.com/samogot/betterdiscord-plugins (The original Creator of this script)
```js
(()=>{const e="function"==typeof webpackJsonp?webpackJsonp([],{__extra_id__:(e,t,n)=>t.default=n},["__extra_id__"]).default:webpackJsonp.push([[],{__extra_id__:(e,t,n)=>e.exports=n},[["__extra_id__"]]]);delete e.m.__extra_id__,delete e.c.__extra_id__;Object.defineProperty(((t,n)=>((t,n={})=>{const{cacheOnly:l=!0}=n;for(let n in e.c)if(e.c.hasOwnProperty(n)){let l=e.c[n].exports;if(l&&l.__esModule&&l.default&&t(l.default))return l.default;if(l&&t(l))return l}if(l)return console.warn("Cannot find loaded module in cache"),null;console.warn("Cannot find loaded module in cache. Loading all modules may have unexpected side effects");for(let n=0;n<e.m.length;++n)try{let l=e(n);if(l&&l.__esModule&&l.default&&t(l.default))return l.default;if(l&&t(l))return l}catch(e){}return console.warn("Cannot find module"),null})(e=>t.every(t=>void 0!==e[t]),n))(["isDeveloper"]),"isDeveloper",{get:e=>1,set:e=>e,configurable:!0})})();
```
## Get all Badges
This script enables all Badges on you client. Note that other users won't see them.<br>
all credit to rezizt and zebratic
![preview]()
This isn't a fake screenshot your client will really display this
```js
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().flags=-1
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().public_flags=-1
```

## Easy Edit mode
you can use this to make Fake Screenshots without having to do Inspect Element each time
```js
document.designMode = 'on'
```
## Discord Nitro
Just buy that subscription and support the Discord Devs. This is just a experiment that probably doesn't even work.
Credit to https://github.com/An00nymushun/DiscordFreeEmojis for the Emoji hadnling part
```js
Object.values(webpackJsonp.push([[],{[''] :(_,e,r)=>{e.cache=r.c}},
[['']]]).cache).find(m=>m.exports&&m.exports.default&&m.exports.default.getCurrentUser!==void
0).exports.default.getCurrentUser().premium_type=2
var node = documuent.createElement('style');
node.appendChild(document.createTextNode('.emojiItemDisabled-1FvFuF{filter: grayscale(0%);}'));
document.getElementsByTagName('head')[0].appendChild(node);
!function(){"use strict";var e,o={Log:e=>{console.log(`%c[NitroHack_hxr404] %c${e}`,"color:#0cf;font-weight:bold","")},Warn:e=>{console.warn(`%c[NitroHack_hxr404] %c${e}`,"color:#0cf;font-weight:bold","")},Error:e=>{console.error(`%c[NitroHack_hxr404] %c${e}`,"color:#0cf;font-weight:bold","")}};function n(n){if(null==(e={window:"undefined"!=typeof unsafeWindow?unsafeWindow:window}).window.webpackJsonp)return n||o.Error("Webpack not found."),0;const t="function"==typeof e.window.webpackJsonp?e.window.webpackJsonp([],{__extra_id__:(e,o,n)=>{o.default=n}},["__extra_id__"]).default:e.window.webpackJsonp.push([[],{__extra_id__:(e,o,n)=>{e.exports=n}},[["__extra_id__"]]]);delete t.m.__extra_id__,delete t.c.__extra_id__;const i=(e,o)=>((e,o)=>{for(let o in t.c)if(t.c.hasOwnProperty(o)){let n=t.c[o].exports;if(!n)continue;if(n.__esModule&&n.default&&(n=n.default),e(n))return n}if(!o){console.warn("Couldn't find module in existing cache. Loading all modules.");for(let o=0;o<t.m.length;o++)try{let n=t(o);if(!n)continue;if(n.__esModule&&n.default&&(n=n.default),e(n))return n}catch(e){}console.warn("Cannot find module.")}return null})(o=>e.every(e=>void 0!==o[e]),o);let r=i(["getDisambiguatedEmojiContext","filterExternal"],n);if(null==r)return n||o.Error("emojisModule not found."),0;let l=i(["parse","parsePreprocessor","unparse"],n);if(null==l)return n||o.Error("messageEmojiParserModule not found."),0;let a=i(["useEmojiSelectHandler"],n);if(null==a)return n||o.Error("emojiPickerModule not found."),0;r.filterExternal;r.filterExternal=function(e,o,n){let t=r.getDisambiguatedEmojiContext(e?e.guild_id:null).nameMatchesChain(o);return n>0&&(t=t.take(n)),t.value()};const u=l.parse;l.parse=function(){let e=u.apply(this,arguments);if(0!==e.invalidEmojis.length){for(let o of e.invalidEmojis)e.content=e.content.replace(`<${o.animated?"a":""}:${o.originalName||o.name}:${o.id}>`,o.url.split("?")[0]+"?size=64");e.invalidEmojis=[]}return e};const c=a.useEmojiSelectHandler;return a.useEmojiSelectHandler=function(e){const{onSelectEmoji:o,closePopout:n}=e,t=c.apply(this,arguments);return function(e,i){if(i.toggleFavorite)return t.apply(this,arguments);const r=e.emoji;null!=r&&r.available&&(o(r,i.isFinalSelection),i.isFinalSelection&&n())}},o.Log("loaded"),1}var t=0;!function e(){0===n(!0)&&window.setTimeout(600==++t?n:e,100)}()}();
```

## oauth Bot and System
test. Doesn't work. Don't run this
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
