---
layout: post
title: 'How to use localStorage'
date: 2019-10-22
description: 'How to use localStorage'
category: blog
tag: 
- web development 
- javascript
- coding
- localstorage
---

<figure>
	<img src="../assets/images/posts/local_storage_2.jpeg">
</figure>

LocalStorage is a type of web storage. It allows you to store and retrieve data in the user's browser. The main difference to sessionStorage is that the data is persistent and will stay in the browser forever unless explicitly deleted. With sessionStorage the data will be only be available as long as the user keeps the app tab open.

## The most important methods of localStorage:

-   `setItem()`: Add key and value to localStorage
-   `getItem()`: Retrieve a value by the key from localStorage
-   `removeItem()`: Remove an entry by key from localStorage
-   `clear()`: Clear all localStorage

---

## `setItem()`

You create key/value pair entries with `setItem()`, providing a key and a value:

```js
// what you need to know about me
let myDetails = {
    name: 'Simona',
    hobbies: ['reading', 'sleeping'],
    cats: ['Fetti', 'Diego'],
    loves: 'Robots'
};

// add key/value pairs to your localStorage
// to store JS objects you need to serialise them first
localStorage.setItem('details', JSON.stringify(myDetails));
localStorage.setItem('favouriteBook', '"Until I Find You", by John Irving');
localStorage.setItem('currentMood', 'grumpy');
```

You update entries with `setItem()` using the same key.

---

## `getItem()`

To retrieve entries you use `getItem()`.

```js
// it's a rainy Saturday evening, what am I going to read?
localStorage.getItem('favouriteBook');

// Remember to deserialise to convert to an object again
JSON.parse(localStorage.getItem('details'));
```

---

## `removeItem()`

To delete an entry you use the `removeItem()` method and pass it the key you want to remove:

```js
// someone gave me chocolate, I am no longer grumpy!
localStorage.removeItem('currentMood');
```

---

## `clear()`

The `clear()` method removes **all** entries from your localStorage:

```js
localStorage.clear();
```

## Complete Gist

<script src="https://gist.github.com/winnekes/9c6f103742678021be8a270bf9c15bbe.js"></script>

---

# Caveats

-   localStorage can be accessed by any code, since it has no form of data protection you should not store senstive data in it.
-   Size is limited, you can store between 5-10mb of data in the browser
-   Using localStorage is a synchronous process. Each operation that you run will be executed **one after the other**. Is your application big? Using localStorage is not wise, it will definitely decrease performance