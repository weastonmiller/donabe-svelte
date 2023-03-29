# Svelte - Donabe

## The svelte flavor of the bring your own ingredients markdown article viewer

## Why?

After trying and seemingly failing to get some of the basic gatsby starter templates to work (or even install), I decided to take a step back and decide what I was really looking for in them anyway.

As it turns out, I just wanted a lightweight, performant and accessible web application that would act as a reader for articles written in markdown. With this clearer goal in mind I set to work making this.

**The [React version](https://github.com/weastonmiller/donabe) and this Svelte version are functionally the exact same, with minor implementation changes. This Svelte version was made for fun and also to see how much smaller the build bundle would be and if there would be any performance differences.**

---

## Installation

```
git clone
cd clonedDirectory/
npm install
```

There is 1 article and an about page (which is what the `/about` route uses) left as examples. Everything should work out of the box.

---

## Building

```
npm run build
npm run preview
```

---

## Architecture

The articles are `.md` files written directly in the respository in the `/static/articles` directory. In order to access them on the `/browse` page there is a mapping in the `articles.ts` file in which you give some metadata about the article that looks like this:

```
{
    _id: 0,
    title: `The wonderful expansive world of Japanese Denim`,
    thumbnail:
      'https://assets.bonappetit.com/photos/57c59f63a184a3c9209db716/4:3/w_4911,h_3683,c_limit/hot-pot-donabe-chopsticks.jpg',
    created: 'Monday March 27th, 2023',
    path: '0',
},s
```

**Please note the path having no file extension in this version.**

## Technology

This app is a standalone web app with no server. The `.md` files are stored directly in the repository. Even with multiple pictures and tons of markdown, the article files tend to remain under 4-5kb which feels acceptable.

I tried to keep the libraries to an absolute bare minimum. This uses **no** component libraries The app is viewable on **all** screen sizes (_some extremely esoteric exceptions probably exist_) and I tried to make the app as accessible as possible by using all the correct html tags. _There is still work to be done with better accessibility though_.

All images used in the `/.md` files are references to outside image hosting services like flickr. I would recommend keeping this convention as it will keep you from saving images locally and bloating the size of your repository.

The `/.md` articles are rendered using `svelte-markdown`. There is no compilation or build step as the articles are supplied directly to the renderer.

I have done some of my own component mapping for certain html tags rendered by `svelte-markdown` and these can be found in the `/components` folder. It's small things like making the `h6` tag into a subtitle type tag for images, doing some image width fixing, etc. Feel free to change anything here to your liking.

**Disclaimer** - I did not make this with code rendering in mind, so that will require some setup. As is, it does technically render `<code />` with the default styling supplied by `svelte-markdown` but that's it. [Please refer to their documentation for more information](https://github.com/pablo-abc/svelte-markdown). _It may be possible to do more serious formatting via syntax highlighting, if I am reading this right at least: [shiki-code-highlighting](https://github.com/rodneylab/sveltekit-shiki-code-highlighting)_

---

## Styles

Being more lightweight than the [React version](https://github.com/weastonmiller/donabe), I made no effort to support anything but a very simple list. Since the idea is to be unopinionated as to what your browse page looks like, it is up to you to implement your own styles.

Here is a link to [svelte-bricks](https://github.com/janosh/svelte-bricks) if you want something that looks good out of the box for blog style content with thumbnails.

---

## Images

Since this app is functionally and visually identical to the [React version](https://github.com/weastonmiller/donabe), please refer there for pictures.
