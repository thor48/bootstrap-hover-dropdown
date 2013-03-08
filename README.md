Twitter Bootstrap Hover Dropdown Plugin
=======================================

A simple plugin to enable twitter bootstrap dropdowns to activate on hover and provide a nice user experience.

The dropdowns are dismissed after a configurable delay. This fixes an issue that can instantly close your nav because of a 1px gap between the button/nav item that activated the dropdown and the actual dropdown. It is also generally a better user experience, as users are not punished by going 1 pixel outside of the dropdown, which would instantly close the nav without a delay.

**Note:** The HTML markup is the same as with any other Twitter Bootstrap dropdown. This will not interfere with Bootstrap's default activate-on-click method (i.e. this plugin combined with Bootstrap's default behavior work well to support both the ideal experience on desktop and mobile).

## Usage

Just like in Bootstrap you can activate it without any JavaScript, just by adding a data-attribute, you can make it automatically work.

Add `data-hover="dropdown"` in addition (or in place of) Bootstrap's `data-toggle="dropdown"`.

You can set options via data-attributes, too, via `data-delay` and `data-close-others`. Here's an example of markup:

```html
<li class="dropdown">
    <a href="#" class="dropdown-toggle" data-toggle="dropdown" data-hover="dropdown" data-delay="1000" data-close-others="false">
        Account <b class="caret"></b>
    </a>
    <ul class="dropdown-menu">
        <li><a tabindex="-1" href="#">My Account</a></li>
        <li class="divider"></li>
        <li><a tabindex="-1" href="#">Change Email</a></li>
        <li><a tabindex="-1" href="#">Change Password</a></li>
        <li class="divider"></li>
        <li><a tabindex="-1" href="#">Logout</a></li>
    </ul>
</li>
```

Alternatively, you can initialize via JavaScript:

```javascript
$('.dropdown-toggle').dropdownHover(options);
```

This also works with submenus without any other configuring since Twitter Bootstrap already supports this feature. Just use the markup like you were using before. Only the top level anchor tag needs any special markup for my plugin to work (see demo for proper markup).

## Options

* **delay**: *(optional)* The delay in miliseconds. This is the time to wait before closing a dropdown when the mouse is no longer over the dropdown or the button/nav item that activated it. Defaults to `500`.
* **instantlyCloseOthers**: *(optional)* A boolean value that when true, will instantly close all other dropdowns matched by the selector used when you activate a new navigation. This is nice for when you have dropdowns close together that may overlap. Default is `true`.

## Demo

You can view a demo for this plugin on my site: http://cameronspear.com/demos/twitter-bootstrap-hover-dropdown/

### A Note on Choosing a Selector

This plugin purposedly lets you choose a selector (as opposed to apply this to everything with the class of `.dropdown-toggle`). This is so that you can selectively apply it where you want. Maybe you only want to use it for the main nav, and not have it activate for dropdown buttons in the main content. You can add a class to the item that normally gets `.dropdown-toggle` and use that class with this plugin to easily achieve that, or use a selector such as `.main-nav .dropdown-toggle`.

**Important:** Bootstrap relies on styles associated with the class `.dropdown-toggle` (for stuff like the caret color), and it is recommended you leave that class alone.

## Contributions

[Mattia Larentis](https://github.com/nostalgiaz) helped me with the idea for the data-attributes and doing the options via an object.

## Roadmap

As this plugin, in its simplicity, is pretty much exactly what I intend it to be, I don't plan to implement any new features. **One exception:** I would like to tweak it so that when you're in a submenu, it doesn't instantly close when you hover outside of it.

If you have ideas for a new feature or something along those lines, you're welcome to share them with me, but I am not likely to implement it/merge your pull without a very compelling reason. You are absolutely free to create a fork and implement the feature yourself for your and others' use.

This, of course, does not speak for bugs. If you have a bug, please bring it to my attention, and I will try and fix it. Note that 93.7% of people's issues are caused by incorrect markup, so please double check that first.

## Me

Follow me on Twitter: [@CWSpear](https://twitter.com/CWSpear) or check out my [blog](http://cameronspear.com/blog/).
