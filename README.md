Primero es necesario el instalar vue dentro de la carpeta en la que se va a crear el proyecto con el comando: 
> npm create vue@latest
 luego, con el comando create-vue, sale el menu de creación de la aplicación de forma similar:
 ✔ Project name: … <vue-hello-world>
✔ Add TypeScript? … No / Yes
✔ Add JSX Support? … No / Yes
✔ Add Vue Router for Single Page Application development? … No / Yes
✔ Add Pinia for state management? … No / Yes
✔ Add Vitest for Unit testing? … No / Yes
✔ Add an End-to-End Testing Solution? … No / Cypress / Playwright
✔ Add ESLint for code quality? … No / Yes
✔ Add Prettier for code formatting? … No / Yes

Scaffolding project in ./<vue-hello-world>...
Done.

> cd <vue-hello-world>
> npm install
> npm run dev

The first step is to create a html file that will contain a div with a specific ID attribute which let you tell your JS view: "you will replace this div with my JS app". Edit the index.html file like this:

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My HelloWorld vueJS</title>
  </head>
  <body>
    <div id="myApplication"></div>
  </body>
</html>

// The Vue build version to load with the `import` command
// (runtime-only or standalone) has been set in webpack.base.conf with an alias.
import Vue from 'vue'
import App from './App'

Vue.config.productionTip = false

/* eslint-disable no-new */
new Vue({
  el: '#myApplication',
  template: '<App/>',
  components: { App }
})

Small explanation:

In this file, we imported the View and App classes to be able to use them in the rest of the script.

Then We create our Vue object by passing it in parameter:
- el: the identifier of the element containing our application
- template: the contents of the div, here we put a tag <App /> ie the component "App" that is declared just below. we will defined a template which will replace this tag <App /> .
- component: the View component (ie the .vue file) which will contain 3 parts: logical code, template, css style.
Step 3: Create our App component
A VueJS component is represented by a file ".vue" with the name of its component (here App therefore the file will be called "App.vue").

In this step we will declare our component App to be our only component for our helloworld vueJS.

This component consists of 3 parts contained in tags:
- template: contains the code to display instead of the <App /> tag
- script: contains the javascript code, it is here that we will insert the "logic" of our component.
- style: not required, but always practical if you want to define a particular css style for your element.

So create the file /src/App.vue like this:

<template>
  <div id="myApplication">
    <h1>Hello World</h1>
    <p>little text behind the title</p>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
    
