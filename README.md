# Ðapp styles
*Version 0.1*

These styles give a simple basic layout for your Ðapps.

**Note: This is a very early stage of the package, not all elements are explained, or ready to use. Use it just to try.**

## The Design

The Ethereum Dapp design style is meant to ease the task of designing clear and good looking App interfaces. It uses as few images as possible for the UI and instead uses colors and icons for differentiating hierarchies. In order to make each Dapp unique and help the user quickly realize where he is even when navigating different instances of the same app, we use GeoPatterns in backgrounds when they refer to a unique instance of something. The fonts used are all open source, Source Sans, from Adobe which has a rich family and multiple styles and Montserrat for bold and strong titles. We also use a font for vector icons to ensure scalability and easy customization.

Most apps are different variations of some simple elements: 

* Use the header on the top with tabs, when your Dapp uses a few constant sections (ie. send and receive)

* Use the left sidebar when your Dapp has a large number of sources for content (ie. a list of chats)

* Use the right action bar for actions to be done with the current content 

* Use Dapp-overflow if you want the sections to scroll independently and to remain fixed on the screen

### Screenshots 
**These are early screenshots and many things are bound to change during development**

![Generic contract showing styles](https://cloud.githubusercontent.com/assets/112898/6045448/4eb71c24-ac81-11e4-8498-7a4153530841.png)

![Democracy DAO](https://cloud.githubusercontent.com/assets/112898/6045449/535c483a-ac81-11e4-8957-e2c1cb9af27d.png)

![Democracy DAO - Pink](https://cloud.githubusercontent.com/assets/112898/6045452/5a188a6c-ac81-11e4-9a8c-40eda1dc6faa.png)

![A custom currency contract](https://cloud.githubusercontent.com/assets/112898/6045454/5e2283f6-ac81-11e4-8bc3-727f6ac33b27.png)


![An Escrow contract](https://cloud.githubusercontent.com/assets/112898/6045463/6952295c-ac81-11e4-8e2b-76b7f7e38b3c.png)

![Chat Application](https://cloud.githubusercontent.com/assets/112898/6045468/6e9d2ee8-ac81-11e4-8d17-79762336ed4d.png)


![Chat application, profile view](https://cloud.githubusercontent.com/assets/112898/6045469/7316d3ca-ac81-11e4-8855-5a88fc0ac92e.png)



## Setup


### CSS
To use it as CSS file just link the css file from the `dist/` folder. **(No done yet.. sorry, compile yourself please)**


### LESS
To use it as less file, which would allow you to overwrite all constants 
from the `constant.import.less` and use the mixins from `mixins.import.less`.
Just link the `dapp-styles.less` in your apps main LESS file.

### Meteor
To use it in a Meteor app add the `less` package:

    $ meteor add less

Copy this dapp-styles repo content into your apps `public` folder under `public/dapp-styles/`
and link to the `dapp-styles.less` in the main LESS file of your project with:

    @import 'public/dapp-styles/dapp-styles.less';



## Usage

A full layout consists of the following HTML elements:

```html

<header class="dapp-header">
    
</header>

<div class="dapp-flex-content">
    
    <!-- aside -->
    <aside class="dapp-aside">

    </aside>

    <!-- content-->
    <main class="dapp-content">
        
    </main>

    <!-- actionbar -->
    <aside class="dapp-actionbar">

    </aside>

</div>

<!-- footer -->
<footer class="dapp-footer">
    
</footer>

```

This gives you a basic flex box layout with a fixed header height and footer height, and a growable content area.

**Note: You can remove any part (header, footer, asides) of it and still have nice fitting containers.**

### Using overflow auto in containers

If you want the apps area to be maximal the window size and the content of your containers to be `overflow: auto`,
just add the `dapp-overflow` class to the `dapp-header`, `dapp-content`, `dapp-footer`, `dapp-actionbar` and/or `dapp-aside` containers and add the following to your main CSS file:

```css
html, body {
    height: 100%;
}
```

### Mixins

When you use the less version of the framework you will be able
to use all its LESS mixins including the LESSHAT mixins (https://github.com/madebysource/lesshat, which are used by the dapp-styles) in your own LESS files.

### Elements

TODO

#### Menus

To add a header or aside menu just add the follwowing structure to your `.dapp-header` or `dapp-aside` container:

```html
<nav>
    <ul>
        <li>
            <a href="#" class="active">
                <i class="icon-arrow-down3"></i>
                <span>Receive</span>
            </a>
            <a href="#">
                <i class="icon-arrow-up2"></i>
                <span>Send</span>
            </a>
        </li>
    </ul>
</nav>
```



