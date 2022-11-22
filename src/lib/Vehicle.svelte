<script>
  import Core from './Core.svelte'
  import Battery from './Battery.svelte'
  import Scanner from './Scanner.svelte'
  export let title
</script>

<div class="jumbotron p-2 bg-dark">
  <h2 class="text-white float-right"><small>{title}</small></h2>
  <ul class="nav nav-tabs" id="myTab" role="tablist">
    <li class="nav-item">
      <a class="nav-link active" id="home-tab" data-toggle="tab" href="#components" role="tab" aria-controls="home" aria-selected="true">Components</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="profile-tab" data-toggle="tab" href="#profile" role="tab" aria-controls="profile" aria-selected="false">Profile</a>
    </li>
    <li class="nav-item">
      <a class="nav-link" id="contact-tab" data-toggle="tab" href="#contact" role="tab" aria-controls="contact" aria-selected="false">Contact</a>
    </li>
  </ul>
  <div class="tab-content p-3 bg-white" id="myTabContent">
    <div class="tab-pane fade show active" id="components" role="tabpanel" aria-labelledby="home-tab">
      <div class="card-deck">
        <Core/>
        <Battery/>
        <Scanner />
      </div>
    </div>
    <div class="tab-pane fade" id="profile" role="tabpanel" aria-labelledby="profile-tab">...</div>
    <div class="tab-pane fade" id="contact" role="tabpanel" aria-labelledby="contact-tab">...</div>
  </div>
</div>
