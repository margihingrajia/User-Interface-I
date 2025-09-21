<script>
  export let entries = {};
  let type = "";
  let rash = false;

  function update() {
    entries.diaper = { type, rash };
  }
</script>

<div class="card" style="background:#fff0f6;">
  <h2>Diaper</h2>
  <select bind:value={type} on:change={update}>
    <option value="">Select</option>
    <option value="wet">Wet</option>
    <option value="dirty">Dirty</option>
    <option value="dry">Dry</option>
  </select>
  <label><input type="checkbox" bind:checked={rash} on:change={update}/> Rash?</label>
</div>
