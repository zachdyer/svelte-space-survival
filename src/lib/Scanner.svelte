<script>
  import Component from './Component.svelte'
  import {batteryLevel} from './stores.js'
  let progressStyle = "progress-bar-striped bg-success"
  let scannerDuration = 10
  let scanning = false
  let scannerTime = 0
  let buttons = [
    {
      title: "Scan Area", 
      handler: ()=>{
        progressStyle = "progress-bar-striped progress-bar-animated bg-success"
        if(!scanning) {
          scanning = true
          let loop = setInterval(()=>{
            scannerTime++
            batteryLevel.update(value => value - 1)
            scannerProgress += 10
            if(scannerTime >= scannerDuration) {
              clearInterval(loop)
              scanning = false
              progressStyle = "progress-bar-striped bg-success"
              scannerTime = 0
              setTimeout(()=>scannerProgress = 0,1000)
            }
          }, 1000)
        }

      }
    }
  ]
  let scannerProgress = 0
</script>

<Component 
  title="Scanner" 
  text="Use the scanner to gather data about your surroundings." 
  img="/img/radar.jpg"
  buttons={buttons}
  progressValue={scannerProgress}
  progressMax={100}
  progressStyle={progressStyle}
/>