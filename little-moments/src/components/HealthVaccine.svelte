<script>
  export let entries = {};
  let vaccineName = "";
  let date = "";

  function update() {
    entries.health = { vaccineName, date };
  }
</script>

<div class="card" style="background:#c8e6c9;">
  <h2>Health / Vaccine</h2>
  <input type="text" placeholder="Vaccine Name" bind:value={vaccineName} on:input={update} />
  <br />
  <input type="date" bind:value={date} on:change={update} />
</div>
