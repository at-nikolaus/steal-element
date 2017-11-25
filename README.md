# steal-element
StealJS Element to dedublicate Steal Loading and other optimizations like supplying a diffrent scope to steal-module

## Example with steal-module
```html
<!-- Global -->
<steal>
  // Steal module code here like Steal.import
  // This is not scoped so this innerText === Steal Module
</steal>
<steal-module>
  // Steal Module with global window.Steal 
  // Steal.import
</steal-module>
```

```html
<!-- Scoped The Steal tag it self holds a own Steal version that can be shared via selecting the tag-->
<steal baseURL="" scoped>
  <!-- All steal-module tags between the Tag is using this.currentScript.Steal -->
  <h1>I am Scoped</h1>
  <!-- When scoped is set this is not a script tag content its HTML element-->
  <steal-module>
  // All between the Tag is using this.currentScript.Steal
  //import myView ...
  </steal-module>
</steal>
```
