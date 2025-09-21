<script>
  export let entries = {};
  let start = "";
  let end = "";
  let total = "";

  function update() {
    entries.sleep = { start, end, total };
  }
</script>

<div class="card" style="background:#f0f4c3;">
  <h2>Sleep</h2>
  <label>Start Time: <input type="time" bind:value={start} on:change={update} /></label>
  <br />
  <label>End Time: <input type="time" bind:value={end} on:change={update} /></label>
  <br />
  <label>Total Hours: <input type="number" min="0" step="0.5" bind:value={total} on:input={update} /></label>
</div>
