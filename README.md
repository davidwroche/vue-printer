<p align="center">
  <img width="250px" height="250" src="vue-printer.png">
</p>

# 

- __Lead Maintainer:__ [David Roche][Lead]


Vue printer is a plugin for vue js. Pass in any component to vue-printer as a prop. 
You can then print that component itself rather than the entire page.


- Post a [github issue][Issue],


## Install
To install via npm,

```
install vue-printer
```

## Quick Example



```html

<template>
  <div id="app">
    <random v-if="printer_off"></random>
 
    <printer :printcomponent="$options.components.test"  @printerStatus="printer_off = $event" :printer_off="printer_off"></printer>
  </div>
</template>

```

```js
import printer from "vue-printer";
import test from "vue-test"; // just shows where $options.components.test is from


export default {
  name: "app",
  components: {
    printer,
    test
  },
  data() {
    return {
      printer_off: true
    };
  }
};

```

```css
<style>

</style>

```

## How it works

Pass in the component you would like to be able to print here

:printcomponent="$options.components.test" 

So replace .test with the name of your component.

Your component will be added into the printer component. When the component is clicked a

window will popup allowing you to print the page. 

The child printer component emits an event to parent component telling it wants to print. The parent sets printer_off to false which hides other components. We pass the value of printer_off
to the child printer as a prop. Printer is watching this value and in turn knows when you are ready to print. 

After you print, the printer component will show other components again.



## Contributing

If you feel you can help in any way, be
it with bug reporting, documentation, examples, extra testing, or new features feel free
to [create an issue][Issue], or better yet, [submit a [Pull Request][Pull]. 




[Issue]: https://github.com/davidwroche/vue-printer/issues
[Lead]: https://github.com/davidwroche
[Npm]: https://www.npmjs.com/package/vue-printer
[Pull]: https://github.com/davidwroche/vue-printer/pulls
