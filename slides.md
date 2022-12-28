---
theme: unicorn
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Toasts slides
  Presentation that showcases some toasts.
drawings:
  persist: false
title: Toasts 🍞🍞🍞
---

# Toasts

🍞🍞🍞

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>
---

# What's a toast?

<div>
  <div class="flex flex-row items-center justify-between">
    <span class="max-w-xl block w-full">A toast is a graphical element that lets us show notifications to users without demanding their immediate attention, unlike modals.</span>
    <span @click="showToast" class="mr-8 px-2 cursor-pointer py-1 bg-gradient-to-br from-purple-200 to-pink-300 shadow-lg focus:outline-transparent text-black text-opacity-80 font-bold rounded transform hover:-translate-y-1 transition">Show me a toast</span>
  </div>
</div>

<script setup lang="ts">
function examplePromise() {
 return new Promise((resolve, reject) => {
    setTimeout(() => {
      const toastIsFine = Math.random() > 0.2;
      if (toastIsFine) {
        resolve('Perfect toast')
      } else {
        reject('Burnt toast')
      }
    }, 1000)
  })
}

function showToast() {
  toaster.promise(examplePromise(), { loading: 'Preparing toast' })
}
</script>

---

<span class="text-center text-6xl font-bold block">Motivation</span>

---

<div class="text-center">
  <h1>Boosts overall UX</h1>
  <span>SuiteCommerce sites usually lack good UX in terms of showing notifications or loading progress.</span>

  <img src="https://i.imgur.com/PfICKCs.gif" class="w-80 mt-4 mx-auto">
</div>

---


<div class="text-center">
  <h1>Easy to implement</h1>
  <span>in any scenario where asynchronous operations are present.</span>

  <img src="https://i.imgur.com/geBhosy.gif" class="w-80 mt-4 mx-auto h-24 object-cover object-top">
  <img src="https://i.imgur.com/UwxdLfT.gif" class="w-80 mt-4 mx-auto h-24 object-cover object-top">
</div>

---

<div class="text-center">
  <span class="text-center text-6xl font-bold block mb-8">Approach</span>
  <span class="text-sm italic mb-8 opacity-75">Toasts were originally created in Egypt about 3000 years ago, with the invention of the oven.</span>

  <p class="mt-8" v-click>
    <a target="_blank" href="https://github.com/BrokenRubik/svelte-toasts">Lightweight promise-based Svelte library that implements toast notifications 🍞.</a>
  </p>

  <p v-click>
    <a target="_blank" href="https://github.com/br-lucas/toasts-dist/tree/main/dist">Bundled script is only 6 kB, and optional base styles can be imported separately.</a>
  </p>
</div>
---

<div class="text-center relative">
  <h1>Basic Implementation</h1>
  <span class="text-sm italic opacity-75 block">A basic SuiteCommerce extension was developed to showcase a simplee implementation of the library on an empty store.</span>
  <span class="text-sm italic mt-4 opacity-75 block">However, the main idea behind toast notifications is that each site has unique implementations for their customizations.</span>

  <img src="https://i.imgur.com/Viktf1S.gif" class="mx-auto w-full px-32 object-cover absolute">
  <img v-click src="https://i.imgur.com/1qWWTqa.gif" class="mx-auto w-full px-32 object-cover absolute z-25">
  <img v-click src="https://i.imgur.com/lQ3OAr2.gif" class="mx-auto w-full px-32 object-cover z-50 relative">
</div>

---

# Here's some code


<div class="flex flex-row gap-12 justify-start m-2">
```ts {all|1,12|2,11|3,10|4|5-6|8|1-13|14-16}
function examplePromise() {
 return new Promise((resolve, reject) => {
    setTimeout(() => {
      const toastIsFine = Math.random() > 0.2;
      if (toastIsFine) {
        resolve('Perfect toast')
      } else {
        reject('Burnt toast')
      }
    }, 1000)
  })
}

function showToast() {
  toaster.promise(examplePromise(), { loading: 'Preparing toast' })
}
```

<div>
 <span @click="showToast" class="mb-8 inline-block px-2 cursor-pointer py-1 bg-gradient-to-br from-purple-200 to-pink-300 shadow-lg focus:outline-transparent text-black text-opacity-80 font-bold rounded transform hover:-translate-y-1 transition">Show me a toast</span>

* Promise-based
* Platform-agnostic
* Lightweight (powered by [Svelte](https://svelte.dev/))

</div>
</div>

<script setup lang="ts">
function examplePromise() {
 return new Promise((resolve, reject) => {
    setTimeout(() => {
      const toastIsFine = Math.random() > 0.2;
      if (toastIsFine) {
        resolve('Perfect toast')
      } else {
        reject('Burnt toast')
      }
    }, 1000)
  })
}

function showToast() {
  toaster.promise(examplePromise(), { loading: 'Preparing toast' })
}
</script>

---


<div class="text-center mx-auto">
  <h1>API</h1>
  <span class="text-sm italic opacity-75 block">Simple API. Compatible with jQuery promises.</span>

  <div class="text-left mx-auto max-w-3xl">

  ```ts
  // Instant notifications
  toaster.success('Success!');
  toaster.success('Can be configurable', { minWidth: 300, duration: 5000 });

  toaster.error('User not found!', { duration: 1000 });


  // Promise notifications
  toaster.promise(promise: Promise<any>, 
    { 
      loading: string   // This text will be displayed while the promise is loading.
      duration: number, // Duration of the promise in milliseconds.
      error: string,    // Error text, can be left blank if the promise rejection returns a string.
      success: string   // Success text, can be left blank if the promise resolution returns a string.
    }
  )
  ```

  </div>

  <span class="rounded bg-black mt-8 inline-block shadow text-white px-2 py-1 text-sm">ℹ️ You can play around with the <b class="text-rose-500">toaster</b> object in the console right now!</span>

</div>

