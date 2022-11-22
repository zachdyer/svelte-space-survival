<script>
  import Component from './Component.svelte'
  let buttons = [
    {
      title: "Scan Area", 
      handler: ()=>{
        console.log('scanning...')
      }
    }
  ]
</script>

<Component 
  title="Scanner" 
  text="Use the scanner to gather data about your surroundings." 
  img="/img/radar.jpg"
  buttons={buttons}
/>