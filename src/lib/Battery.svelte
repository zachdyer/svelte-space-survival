<script>
  import Component from './Component.svelte'
  let batteryCompacity = 100
  let batteryCharge = 100
  let batteryImg = "/img/vite.svg"
  function discharge() {
    batteryCharge--
    if(batteryCharge < 0) batteryCharge = 0
  }
  function charge() {
    batteryCharge++
    if(batteryCharge > batteryCompacity) batteryCharge = batteryCompacity
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
/>