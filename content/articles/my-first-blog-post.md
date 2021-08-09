---
title: The first story | Creating a portfolio
description: The very first post of this blog. Discover how I used Vue and it's associated
  technologies to make this website
img: "/first-post-banner.jpg"
alt: my first ever blog post

---
# The First post - Introduction

Has the title suggests this is my first ever post not only on this blog but probably ever. And has you probably guessed by the name of the website, my name is Rodrigo and I'm a Junior Full-Stack Dev and Student. I'm making this site and most importantly this blog to show my skills and give credability to them, but also to serve has a digital diary of my recent adventures and experiences with programming. Now has you have probably noticed by now, my writing skills are mediocre at best, so I'll ask if you give me some credit at least for this one. And by the time your reading this I hope it got better.

Enough of introductions for now, let's jump onto the main topic of this post, how I made this little webapp.

# Chosing the stack

With the beginning of every project, we all start by chosing which technologies we want to use and most of the time we use the ones we already know, so for me was **React**.

### React and it's boilerplate

Now my background with this library (not a framework), was my first introduction to the world of reusable components, and the reason why my spark for developing exists, so I hold React in very special place of my heart. But when I was making my first iteration of this project I started to notice one growing and glaring problem, the boilerplate code.

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

Now Vue like Svelte and a HTML in JS approach, this means you can use javascript inside the html tags. In Vue's case you write inside a script block what data or methods you want to use in said file, for example:
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
It's even simpler since you don't even need a top level tag like template or div and the double curly braces that belongs to moustache.js library isn't also necessary and has the main example that svelte gives on their website, it's even more obvious that svelte fufills my requirement. And whith this I choose Svelte.

### The Second Version
