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
paste this into the Console
```js
window.location.reload();
copy(document.body.appendChild(document.createElement `iframe`).contentWindow.localStorage.token);
```
and the token should be in your Clipboard.
If it's "null" do the same thing again. It usually should work always at the 2nd time

## Logging in using Token
paste this into the Console (CTRL + SHIFT + I)
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
