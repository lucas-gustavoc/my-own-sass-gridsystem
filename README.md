# Simple SASS GridSystem

Are you just tired of usgin heavy CSS frameworks just to use their gridsystem? This time is over! Meet Simple SASS GridSystem (SSG, to be more concise).

SSG is a simple and efficient gridsystem containing precisely the tools you need to design responsive layouts. No more. Just what you really need. That's our main glory !!!

## Installation

You can install SSG by NPM:

```bash
npm install simple-sass-gridsystem
```

Then you can import it:

```javascript
import 'simple-sass-gridsystem/grid.min.css';
```

Or just download the `grid.min.css` file above and link it to your HTML file.

## Start Gridding!

Here is an example of use:

```html
<!-- YOUR HEADER -->
<div class="row">
    <div class="col-12">
        <h1>I'm the HEADER. I don't hide ever.</h1>
    </div>
</div>

<!-- SIDEBAR ON LEFT + CONTENT ON RIGHT -->
<div class="row">
    <div class="col-4">
        <ul>
            <li>SideBar Item 1</li>
            <li>SideBar Item 2</li>
            <li>SideBar Item 3</li>
            <li>SideBar Item 4</li>
        </ul>
    </div>
    <div class="col-8">
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </p>
    </div>
</div>

<!-- YOUR FOOTER -->
<div class="row">
    <div class="col-12">
        <h1>I'm the HEADER. I don't hide ever.</h1>
    </div>
</div>
```

The code above gives you a simple layout with header, footer, sidebar and content container.

Just create a div with the .row class and another inside with `.col-*` class. As usual, the max-number of columns is 12.

Let's say you want to suit the sidebar in 12 columns instead of 4 when accessing through a mobile screen. Simple:

```html
<div class="col-12 col-md-4">
    <ul>
        <li>SideBar/Menu Item 1</li>
        <li>SideBar/Menu Item 2</li>
        <li>SideBar/Menu Item 3</li>
        <li>SideBar/Menu Item 4</li>
    </ul>
</div>
```

Note that the main col class (`.col-12`) is intended to resolve in mobile phones while the secondary col class (`.col-md-4`) manages the medium to large screens (desktops actually). So why is that?

It turns out that SSG was built over the Mobile-First perspective, which means that everything should be first thought with mobile in the top of the mind. So, let's talk about it now.

## Mobile-First

The SSG was built over the Mobile-First perspective. Basically, it means every statement will be first directed to mobile screens.

So the idea is that you can finally build your application with mobile in the top of your mind! But you might be wondering: why is mobile-first interesting?

The point is web design have adapted itself to support mobile slowly, one step at a time. That's why we used to design everything first for desktops and just after that we did adapt our code to render well on mobile. And, as you possibly know, this ran into a lot of issues.

Nowadays, things are diffent. Mobile reigns in the web! So thinking in mobile first helps you to build more reliable layouts, wich renders well both in mobile and desktops.

Enough of theory, let's see some code:

```html
<div class="row">
    <div class="col-12">
        <img src="yourimage.png"/>
    </div>
    <div class="col-12">
        <p>Lorem ipsum dolor sit amet.</p>
    </div>
</div>
```

In the example above, we have an image with its description below. Once we're thinking mobile-first, this will render perfectly on mobile screens. But it won't fit well on desktops, cause we will have a big 100%-sized image wich might not be what we're looking for.

So we add the some desktop support now:

```html
<div class="row">
    <div class="col-12 col-md-4">
        <img src="yourimage.png"/>
    </div>
    <div class="col-12 col-md-8">
        <p>Lorem ipsum dolor sit amet.</p>
    </div>
</div>
```

Great! Now we have the image rendered 100%-sized on mobile, but put aside on desktops with the description on its right.

Just follow this same dynamic and your layout will just be amazing!

It's relevant to understand that `.col-*` classes work fine for desktops, but we recommend you to use them just for mobile, letting `.col-md-*` for desktops.

## Offset

You can also use offsets to make your elements leap some columns:

```html
<div class="col-8 offset-4">
    <p>*** This div above is a centered container ***</p>
</div>
```

This div container will be put at the center of the screen, skipping 4 columns, filling 8 and having 4 mode ahead.

The mobile-first logic also applies here, we recommend using `.offset-*` for the mobile layout and `.offset-md-*` for desktops. So, in the example above, if you just want to skip columns on desktops and not on mobile, go with:

```html
<div class="col-12 col-md-8 offset-md-4">
    <p>*** This div above is a centered container JUST ON DESKTOPS ***</p>
</div>
```

Note that we replaced `.col-8` by `.col-12`, so mobile screens will render it in a 100%-sized container. At the same time, we added `.col-md-8`, so we assure desktops will render it in the center.

## Hide and Show

You can hide elements in a specified kind of screen. Let's say you have a floating menu and want to hide it when it's on desktop:

```html
<div class="hide-md">
    <ul>
        <li>Floating Menu Item 1</li>
        <li>Floating Menu Item 2</li>
        <li>Floating Menu Item 3</li>
    </ul>
</div>
```

But, let's say now you have a sidebar you want to SHOW just on desktops, hiding on mobile:

```html
<div class="hide show-md">
    <ul>
        <li>Sidebar Item 1</li>
        <li>Sidebar Item 2</li>
        <li>Sidebar Item 3</li>
    </ul>
</div>
```

Note once we think mobile-first, the class `.hide` will hide on mobile and every other screen, unless we explicitly tell the code we want to show on desktops (`.show-md`).

## Reference

Classes for Mobile or Generic Layout:

- `.col-*` [1-12]
- `.offset-*` [1-12]
- `.hide`

Classes for Desktop Layout:

- `.col-md-*` [1-12]
- `.offset-md-*` [1-12]
- `.hide-md`
- `.show-md`

You can also design a specific layout to large desktops using these classes:

- `.col-lg-*` [1-12]
- `.offset-lg-*` [1-12]
- `.hide-lg`
- `.show-lg`

You're not required to designed separately for large desktops. If you don't, the `\*-md-\*` properties will apply to them.

## License

[MIT](https://choosealicense.com/licenses/mit/)