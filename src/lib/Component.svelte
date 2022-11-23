<script>
  export let title
  export let text
  export let progressMax = 100
  export let progressMin = 0
  export let progressValue
  $: progressWidth = (progressValue / progressMax) * 100
  export let img
  export let listItems = []
  export let buttons = []
  export let progressStyle
</script>
<div class="card">
  {#if progressValue }
  <div class="progress rounded-0">
    <div class="progress-bar {progressStyle}" role="progressbar" style="width: {progressWidth}%" aria-valuenow={progressValue} aria-valuemin={progressMin} aria-valuemax={progressMax}></div>
  </div>
  {/if}
  {#if img}<img class="card-img-top" src={img} alt="Card image cap">{/if}
  <div class="card-body">
    {#if title}<h5 class="card-title">{title}</h5>{/if}
    {#if text}<p class="card-text">{text}</p>{/if}
  </div>
  {#if listItems }
  <ul class="list-group list-group-flush">
    {#each listItems as item }
    <li class="list-group-item">{item}</li>
    {/each}
  </ul>
  {/if}
  {#if buttons}
  <div class="card-footer">
    {#each buttons as button}
    <a href="#" class="card-link" on:click={button.handler}>{button.title}</a>
    {/each}
  </div>
  {/if}
</div>
