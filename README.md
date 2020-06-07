## Sapper + Codyframe

<img src="./explanation/sapper and codyframe.png">


This project is a template for Sapper if you want to work with CodyFrame framework ([from Cody House](https://codyhouse.co/ds/docs/framework)) and you want to compile the **SASS files** and useing it directly with **Rollup**

-------------------------------

> Note: You can use this template directly or you can follow the instructions below

-------------------------------

### First things
After getting the template of [sapper](https://sapper.svelte.dev/) for Rollup by:

`npx degit "sveltejs/sapper-template#rollup" my-app`

You have to install the ordinary dependencies by `npm install` and try to run it by : `npm run dev & open http://localhost:3000`

### Issues could happen
If you have this issue *[UnhandledPromiseRejectionWarning: Error: No valid exports main found for /..node_modules/@rollup/pluginutils](https://github.com/sveltejs/sapper/issues/1257)* just remove the `rollup` package from npm and reinstall a new version of it like *"2.13.0"*.

Also if you don't have **Polka** install it by `npm install --save polka`

### Dependencies for SASS compiler
* svelte-preprocess
* autoprefixer
* node-sass

`npm install -D node-sass autoprefixer svelte-preprocess`

or

`yarn add -D node-sass autoprefixer svelte-preprocess`

### Rollup Configurations

<img src="./explanation/01.png">

Inside the **rollup.config.js** file, add these lines outside of *export default* to be accessible globally:

```js
// for sass (codyframe)
import sveltePreprocess from 'svelte-preprocess';
const preprocess = sveltePreprocess({
  scss: {
    includePaths: ['src'],
  },
  postcss: {
    plugins: [require('autoprefixer')],
  },
});
```

Also add these lines in both ***Client and Server*** sections inside of **svelte({...})**:

```js
svelte({
  ...
  preprocess // Add this line
  ...
}),
```

### Get the CodyFrame
Clone the official project from GitHub: [Here](https://github.com/CodyHouse/codyhouse-framework)

We just want the **assets** folder, So copy it inside ***codyframe*** folder in your ***src*** folder.

We want the *style.scss* and *util.js* later.

<img src="./explanation/02.png">

### Sapper Tepmlate File

<img src="./explanation/03.png">

Add these lines in the *template.html* file inside *src* folder:

* in metadata section

```html
<!--  cody framework	 -->
<script>document.getElementsByTagName("html")[0].className += " js";</script>
```
* after `</body>` tag

```html
<!--  cody framework	 -->
<script src="codyframe/util.js"></script>
```

### Sapper Layout File

<img src="./explanation/04.png">

In **_layout.svelte** file inside of *routes* folder, Add these lines directly after`<script>...</script>` lines:

```html
<!-- candy framework SASS - Global -->
<style lang="scss" global>
@import "./codyframe/assets/css/style.scss"
</style>
```

### Last Step!
Don't forget to add ***util.js*** inside of `codyframe` folder in **static** folder of the project

<img src="./explanation/05.png">

### Testing!

In your *`index.svelte`* route, Add any code to test codyframe components, Like this Button:

```html
 <div><button class="btn btn--primary btn--md">Zaki Button!</button></div>
```

### Enjoy!

-----------------------------
Big Thanks to *Sean Schertell*, He wrote a great [article](https://medium.com/@sean_27490/svelte-sapper-with-sass-271fff662da9) about Sapper & Sass :blush: 

Also Thanks to [@HamzaPlus](https://github.com/HamzaPlus) for the IDEA :blush:

<img src="https://raw.githubusercontent.com/zakaria-chahboun/ZakiQtProjects/master/IMAGE2.png" >

My twitter [Zakaria Chahboun](https://twitter.com/zaki_chahboun)
