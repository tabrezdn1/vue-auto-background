# vue-autowrite 


## Purpose
This is a vue component which updates the background with some set of cool colours. This can be used to change the colour automatically in a set of time period or manually. For Example: on a button click. And your HTML content is rendered as a slot.


### Example
```
<AutoBackground ref="autoBackground" :auto="true" :refresh="500">
  <h1>Hello I am slot</h1>
</AutoBackground>
```

### Props
There are currently the following props:

| Prop | Description | Required | Default |
| ------ | ------ | ------ | ------ |
| auto | This prop specifies whether to update the background colour automatically or not. | `true` | As it is required prop so - `null` |
| refresh | This prop is used to specify the refresh rate of updating background colour. It is measured in milliseconds. | `false` | `1000` |

### Slots
There are currently the following slots:

| Slot | Description | Example |
| ------ | ------ | ------ |
| `default` | This is default slot which will be rendered inside the component. prop specifies whether to update the background colour automatically or not.| It is in the above usage Example |

### Manual update
To update the background manually you can trigger inside method using refs. Make sure to mark `auto` prop as `false`, to enable this feature.
Example:
```
<AutoBackground ref="autoBackground" :auto="false" :refresh="500">
      <h1>Hello I am slot</h1>
</AutoBackground>
<button @click="updateBackground()">Update</button>

 methods: {
    updateBackground() {
      this.$refs.autoBackground.updateBackground();
    },
  }

```


## Documentation
Coming soon...
