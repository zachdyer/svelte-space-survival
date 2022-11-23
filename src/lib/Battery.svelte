<script>
  import Component from './Component.svelte'
  import {batteryLevel} from './stores.js'
  let batteryCompacity = 100
  let batteryCharge = 100
  batteryLevel.set(batteryCharge)
  batteryLevel.subscribe(value => batteryCharge = value)
  let batteryImg = "/img/vite.svg"
  function discharge() {
    batteryLevel.update(value => batteryCharge - 1)
    if(batteryCharge < 0) batteryLevel.set(0)
  }
  function charge() {
    batteryLevel.update(value => batteryCharge + 1)
    if(batteryCharge > batteryCompacity) batteryLevel.update(value => batteryCharge = batteryCompacity)
  }
  let batteryButtons = [
    {
      title: "Discharge", 
      handler: discharge
    },
    {
      title: "Charge", 
      handler: charge
    }
  ]
</script>

<Component 
  title="Battery" 
  text="Battery power is required to do anything. The battery is used to store power and track it's usage." 
  progressValue={batteryCharge}
  progressMax={batteryCompacity}
  img={batteryImg}
  buttons={batteryButtons}
  progressStyle="progress-bar-striped bg-warning"
/>