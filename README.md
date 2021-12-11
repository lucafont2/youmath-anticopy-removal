# youmath-anticopy-removal

Create new Tampermonkey script 

// ==UserScript==
// @name         CopyBlock-nograzie
// @namespace    http://tampermonkey.net/
// @version      0.1
// @description  no grazie
// @author       You
// @match        https://www.youmath.it/*
// @match        https://www.chimica-online.it/*
// @icon         https://www.google.com/s2/favicons?domain=youmath.it
// @grant        none
// ==/UserScript==

(function() {
    'use strict';
    var css = '* { user-select: unset !important; }',
    head = document.head || document.getElementsByTagName('head')[0],
    style = document.createElement('style');

    head.appendChild(style);

    style.type = 'text/css';
    if (style.styleSheet){
        style.styleSheet.cssText = css;
    } else {
        style.appendChild(document.createTextNode(css));
    }
    setTimeout(function(){
        document.onmousedown = function(){};
        document.oncontextmenu = function(){};
        document.onclick = function(){};
        document.onselectstart = function(){};
        Event.prototype.preventDefault = function(){};
    },1000);
})();
