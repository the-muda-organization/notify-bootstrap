# Notify Bootstrap
Stylish and modern notifications - small jQuery plugin based on Bootstrap and Font Awesome

New version based on Bootstrap 5 coming soon!

********************************************************************************
## Status
[![GitHub Version](https://img.shields.io/github/release/the-muda-organization/notify-bootstrap.svg?style=for-the-badge)](https://github.com/the-muda-organization/notify-bootstrap)
[![License](https://img.shields.io/github/license/the-muda-organization/notify-bootstrap.svg?style=for-the-badge)](https://github.com/the-muda-organization/notify-bootstrap)


[![Github Star](https://img.shields.io/github/stars/the-muda-organization/notify-bootstrap.svg?style=for-the-badge)](https://github.com/the-muda-organization/notify-bootstrap)
[![Github Fork](https://img.shields.io/github/forks/the-muda-organization/notify-bootstrap.svg?style=for-the-badge)](https://github.com/the-muda-organization/notify-bootstrap)

[![CSS gzip size](https://img.badgesize.io/the-muda-organization/notify-bootstrap/master/dist/css/notify.min.css?compression=gzip&label=CSS+gzip+size)](https://github.com/the-muda-organization/notify-bootstrap/blob/master/dist/css/notify.min.css)
[![JS gzip size](https://img.badgesize.io/the-muda-organization/notify-bootstrap/master/dist/js/notify.min.js?compression=gzip&label=JS+gzip+size)](https://github.com/the-muda-organization/notify-bootstrap/blob/master/dist/js/notify.min.js)


********************************************************************************
## [View DEMO](https://rawcdn.githack.com/the-muda-organization/notify-bootstrap/f50ebe8ffebfefcdea13c7615d8f1294df68f528/DEMO.html)
********************************************************************************

<img src="https://github.com/the-muda-organization/notify-bootstrap/blob/master/PREVIEW.jpg?raw=true" alt="" style="width:100%;display:block;">


********************************************************************************
## Table of contents
- [Status](#status)
- [Quick Start](#quick-start)
- [What's included](#whats-included)
- [Bugs and feature requests](#bugs-and-feature-requests)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Features](#features)
- [CSS Classes](#css-classes)
- [Javascript customize](#javascript-customize)
- [Versioning](#versioning)
- [Changelog](#changelog)
- [Team](#team)
- [Code of Conduct](#code-of-conduct)
- [Copyright and License](#copyright-and-license)


********************************************************************************
## Quick Start

Several options are available:
- [Download the latest release.](https://github.com/the-muda-organization/notify-bootstrap/archive/master.zip)
- Clone the repo: `git clone https://github.com/the-muda-organization/notify-bootstrap.git`
- Install with [Composer](https://getcomposer.org/): `composer require the-muda-organization/notify-bootstrap`


## What's included
Within the download you'll find the following directories and files, logically grouping common assets and providing both compiled and minified variations. You'll see something like this:

There are several dependencies. See below for [Installation Guide](#installation) and [How to Use](#how-to-use)
```
notify-bootstrap/
 │
 └─ dist/
    │
    ├── css/
    │   ├── notify.css
    │   └── notify.min.css
    │
    └── js/
        ├── notify.js
        └── notify.min.js
```


********************************************************************************
## Bugs and feature requests
Have a bug or a feature request? Before opening a new issue search for existing and closed issues. If your problem or idea is not addressed yet, [open a new issue](https://github.com/the-muda-organization/notify-bootstrap/issues/new).


********************************************************************************
## Installation

1. [Download](https://github.com/the-muda-organization/notify-bootstrap/archive/master.zip) and copy files to your project
2. INSTALL DEPENDENCIES:
    - Bootstrap CSS (required)
    - Bootstrap JS  (popper.js NOT required)
    - Font Awesome  (recommended - however you can easily customize with your icon set)
3. You can easily customize CSS and JS (colors, position, time notification is visible, brand icons etc)
4. Add CSS and JS to your project:
```html
    <link href="https://example.com/notify-bootstrap/1.x.x/css/notify.min.css" rel="stylesheet">
    <script src="https://example.com/notify-bootstrap/1.x.x/js/notify.min.js"></script>
```


********************************************************************************
## How to Use

Notify is easy to use. Call the function and provide type, title and message:
```js
notify(type, title, message);
```

Example with jQuery:
```js
$('#button-1').on('click',function(){
    notify('bell','Title of the message!','This is a sample message! Lorem ipsum!');
});
```

Example with javascript:
```js
myElement.addEventListener('click',function(){
    notify('shield-check','Title of the message!','This is a sample message! Lorem ipsum!');
});
```

Notify has a style independend from Bootstrap toast. You can use notify and bootstrap toast component at the same time.

Notify javascript rely 100% on Bootstrap. [Check out bootstrap toast component](https://getbootstrap.com/docs/4.5/components/toasts/#javascript-behavior)


********************************************************************************
## Features

#### Position:
set in CSS at Line 13 & 14. Use ``top:0`` or ``bottom:0`` AND ``left:0`` or ``right:0``


#### Type:
You can add as many types as you need and each type can have custom style.

Type is required. If you leave it empty no icon will be displayed but you will see a placeholder from Font Awesome indicating incorrect icon.

Notify has a few types added as default in several categories:

    GENERAL:
    - info
    - warning
    - error
    - success
    - other
    
    BRANDS:
    - facebook
    - github
    - instagram
    - linkedin
    - paypal
    - skype
    - twitter
    - wikipedia
    - youtube
    
    CUSTOM:
    - spinner
    
    FONT AWESOME:
    - Any icon can be added. Just use icon name as type: 'times', 'ban', 'user' etc.
    - If you want to use other icon type (regular, duotone, light or brand) change line 53 in js file.


To add more types add new ``case 'newCustomType':`` in javascript switch with custom icon and set custom CSS as ``.toast[data-type="newCustomType"]{}``

#### Title:
Anything can be added as title but text is recommended. Title CAN be empty.

#### Message:
Anything can be added as message but text is recommended. Message as well as title CAN be empty.

#### Autohide:
Notification can hide when you click the close button or after a period of time.

    Notify JS Line 60 - autohide - set true or false
    Notify JS Line 61 - custom time to hide notification. Currently it's 5000ms.

#### Animation:
There is no custom animation. Notify uses Bootstrap to show and hide toasts. Feel free to add your own.

#### Custom toast:
Notify uses custom CSS so it is possible to use Bootstrap. All custom style is based on ``[data-type]`` as type should be declared in each notification.


#### Custom Features:
Notify has only basic options so you can easily customize all the code. You can add custom timing for each notification, images,  buttons with links, anything you want.
In Notify Line 7 just add more event objects and call them with ``notify();`` function!


********************************************************************************
## CSS Classes

CSS class                                   | Explanation
------------------------------------------- | -------------------------------------------
``.toast-container``                        | main container for stacking toasts. Set position here.
``.toast``                                  | toast - override from bootstrap
``.toast[data-type]``                       | toast - style for notify not affecting bootstrap toast
``.toast[data-type] .toast-content``        | toast content
``.toast[data-type] .toast-icon svg``       | toast svg icon
``.toast[data-type] .toast-body``           | toast body - it contains title and message
``.toast[data-type] .toast-body strong``    | toast title
``.toast[data-type] .toast-body div``       | toast message
``.toast[data-type] .close``                | toast close button
``.toast[data-type="XXXXXXX"]``             | custom style for a specific notification type (success, error, info etc)


********************************************************************************
## Javascript customize

- **Line 25** - close button svg - now it's Font Awesome ``fas fa-times`` icon
- **Lines 29-54** - Icons for different notification type (success, error, info, brands etc). Font Awesome icons are inlined so they are displayed properly and without delay.
- **Line 53** - You can change default Font Awesome icon style (solid, regular, light, duotone, brands)
- **Line 61** - Set ``autohide (true|false)`` if you want notification to hide after some time
- **Line 61** - Set your own time how long notification should be visible. Currently it is ``5000ms``.
- **Line 67** - It contains toast content template


********************************************************************************
## Versioning
Notify Bootstrap will be maintained under the Semantic Versioning guidelines as much as possible. Releases will be numbered with the following format:
```<major>.<minor>.<patch>```


********************************************************************************
## Changelog
For last releases see detailed [CHANGELOG](https://github.com/the-muda-organization/notify-bootstrap/blob/master/CHANGELOG.md).


********************************************************************************
## Team
-  [Jakub Muda](https://github.com/jakubmuda)


********************************************************************************
## Code of conduct
We will behave ourselves if you behave yourselves. For more details see our
[CODE_OF_CONDUCT.md](https://github.com/the-muda-organization/notify-bootstrap/blob/master/CODE_OF_CONDUCT.md).


********************************************************************************
## Copyright and license
Code and documentation copyright 2017-2020 [The MUDA Organization](https://muda.pl).

Code released under the [MIT License](https://github.com/the-muda-organization/notify-bootstrap/blob/master/LICENSE).


********************************************************************************


