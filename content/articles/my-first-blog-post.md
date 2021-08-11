---
title: The first story | Creating a portfolio
description: The very first post of this blog. Discover how I used Vue and it's associated
  technologies to make this website
img: "/first-post-banner.jpg"
alt: creating my portfolio app

---
# The First post - Introduction

Has the title suggests this is my first ever post not only on this blog but probably ever. And has you probably guessed by the name of the website, my name is Rodrigo and I'm a Junior Full-Stack Dev and Student. I'm making this site and most importantly this blog to show my skills and give credability to them, but also to serve has a digital diary of my recent adventures and experiences with programming. Now has you have probably noticed by now, my writing skills are mediocre at best, so I'll ask if you give me some credit at least for this one. And by the time your reading this I hope it got better.

Enough of introductions for now, let's jump onto the main topic of this post, how I made this little webapp.

# Chosing the stack

With the beginning of every project, we all start by chosing which technologies we want to use and most of the time we use the ones we already know, so for me was **React**.

### React and it's boilerplate

Now my background with this library (not a framework), was my first introduction to the world of reusable components, and the reason why my spark for developing exists, so I hold React in very special place of my heart. But when I was making my first iteration of this project I started to notice one growing and glaring problem, the **boilerplate** code.

At first I was dumbfounded, how can my special tech have this annoyance? I quickly opened a chrome tab and started googling and awestruck with the results, I wasn't the only one. Let me give you an example:

To write a simple paragraph in plain html, you do it like this

```html
<p>A paragraph</p>
```

To write a simple paragraph in react, you can do it like this

```js
ReactDOM.render(
    <p>A paragraph</p>,
    document.getElementById('index')
)
```

Woah what the hell happened, one tag suddendly transformed into a function with two parameters in it. Now this is for a simple paragrah now imagine when you try to write more complex stuff, and let's not even try to talk about state management.

And before you start screaming, React has it's most wonderful uses but in my humble opinion it's not at it's best for something so simple has blog, well at least for what I'm trying to make. And I have a thing for the **DRY** principle, which stands for **D**on't **R**epeat **Y**ourself and all that boilerplate was really hurting that train of thought. So I went back to square one.

### Vue vs Svelte

With a new requirement added I searched for a new framework. And it's two rivals Vue and Svelte looked more appealing than ever. I started with Vue, and I was really impressed not only with the docs but also the CLI and the community, it clearly showed the blood and tears commited to this product.

Both Vue and Svelte use a HTML in JS approach, this means you can use javascript inside the html tags. In Vue's case you write inside a script block what data or methods you want to use in said file, for example:

```vue
<template>
    <p>{{greet}}</p>
    <p>{{upperString(greet)}}</p>
</template>

<script>
    export default {
        data() {
            greet: 'Hello World!'
        },
        methods: {
            upperString(string) {
                return string.toUpperCase()
            }
        }
    }
</script>
```

This will create two paragraphs one with the greet variable and the other with the upperString method, with greet has it's parameter. But the best of all is how the logic is cleanly organized, where all the functions will belong to the methods object and the variables will be part of the data object.

In Svelte's case you can write the same thing above like so:

```js
<script>
    let greet = "Hello World";
    function upperString(string) {
        return string.toUpperCase()
    };
</script>

<p>{greet}</p>
<p>{upperString(greet)}</p>
```

It's even simpler since you don't even need a top level tag like template or div and the double curly braces that belongs to <code>moustache.js</code> library isn't also necessary and has the main example that svelte gives on their <a href="https://svelte.dev/blog/write-less-code" target="blank"/>website</a>, it's even more obvious that svelte fufills my requirement. And with this I choose Svelte to create my portfolio app.

### The Second Version

Starting with svelte is incredibly easy just install one of their templates, I use used their default one, and I used Typescript in this project which is also incredibly easy to do, just use the command <code>node scripts/setupTypescript.js</code> and you're good to go.

 I started with the idea of making a code editor like portfolio and this is as far as I went with the [project](https://github.com/cielos20/Personal-Website "Svelte portfolio"). I spent about two weeks when I encountered a problem a big one in fact, **responsiveness**. While the concept sounded good on paper and looked good on the mockups I couldn't get make good sense of a mobile version. I looked at vs code and visual studio to see how they handled it, which they didn't because it's a desktop app not a mobile one and nowadays people tend to use their phones before the computer. But even so I tried to build it to the best of my abilities.

It didn't took very long until I encountered another dreadful problem, the **routing**. Unfortunately Svelte is still very young and it's routing framework svelteKit is, at the time of this post, in open beta. While it's previous iteration Sapper exists, it will be deprecated and replaced by it's newest self. So while my time with Svelte was  best experience I ever had with javascript in general, it had to come to a close.

### The current iteration

With a new lesson learned I searched for a Vue SSG (Static Site Generator), which returned two frameworks, **NuxtJs** and **Vuepress**. Both could get the job done but one was tailor made for documentation, Vuepress, and the other, Nuxt, was built with a more general purpose in mind and so I choose the latter.

To start a Nuxt project I used the following command:

 `npm init nuxt-app <your-app-name-here>`

This is then followed by several questions about the type of project you want to make and the available technologies you want to use. As for me I choose to add TypeScript for the type safety, Vuetify for styling, Content to create the blog and Jest for testing.

Both Vuetify and Content where new to me and luckily they were easy to learn. Let's start with Vuetify. The docs are pretty damn good and some compenents have some neat examples, like the v-app-bar and v-card. Theming in Vuetify is really easy too. If you're using nuxt, you could find the following lines of code in nuxt.config.js  

 