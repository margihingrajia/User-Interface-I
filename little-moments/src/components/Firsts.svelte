<script>
  export let entries = {};
  let entry = "";
  let suggestion = "";

  const suggestions = [
    "First smile",
    "First crawl",
    "First steps",
    "First words",
    "First tooth"
  ];

  function pickSuggestion() {
    suggestion = suggestions[Math.floor(Math.random() * suggestions.length)];
  }

  function update() {
    entries.firsts = { entry, suggestion };
  }
</script>

<div class="card" style="background:#e1bee7;">
  <h2>Firsts</h2>
  <textarea placeholder="Describe baby's first..." bind:value={entry} on:input={update}></textarea>
  <br />
  <button on:click={pickSuggestion}>Suggest</button>
  {#if suggestion}
    <p>Suggestion: {suggestion}</p>
  {/if}
</div>
