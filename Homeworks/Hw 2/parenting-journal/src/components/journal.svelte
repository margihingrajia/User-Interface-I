<script>
  import { onMount } from 'svelte';

  let date = "";
  let childName = "";
  let mood = "Happy";
  let activities = "";
  let notes = "";

  // Set today's date when the component loads
  onMount(() => {
    const today = new Date();
    date = today.toLocaleDateString();
  });

  function saveEntry() {
    // For now, just alert the entry
    alert(`Journal Entry for ${childName || "your child"} on ${date} saved!\n
Mood: ${mood}
Activities: ${activities}
Notes: ${notes}`);
    
    // Clear inputs after saving
    childName = "";
    mood = "Happy";
    activities = "";
    notes = "";
  }
</script>

<style>
  .journal-container {
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    border: 2px solid #ccc;
    border-radius: 12px;
    background-color: #f9f9f9;
  }

  input, select, textarea {
    width: 100%;
    padding: 8px;
    margin: 6px 0;
    font-size: 16px;
    border-radius: 6px;
    border: 1px solid #ccc;
  }

  button {
    margin-top: 10px;
    padding: 8px 16px;
    font-size: 16px;
    border-radius: 6px;
    cursor: pointer;
    background-color: #4CAF50;
    color: white;
    border: none;
  }

  h2 {
    margin-bottom: 10px;
  }

  p {
    margin-top: 8px;
    white-space: pre-wrap;
  }
</style>

<div class="journal-container">
  <h2>Parenting Journal - {date}</h2>

  <label>Child's Name:</label>
  <input type="text" placeholder="Enter child's name" bind:value={childName} />

  <label>Mood:</label>
  <select bind:value={mood}>
    <option>Happy</option>
    <option>Excited</option>
    <option>Sad</option>
    <option>Angry</option>
    <option>Tired</option>
  </select>

  <label>Activities:</label>
  <textarea placeholder="Describe activities today" bind:value={activities}></textarea>

  <label>Notes / Thoughts:</label>
  <textarea placeholder="Any additional notes..." bind:value={notes}></textarea>

  <button on:click={saveEntry}>Save Entry</button>

  {#if childName || activities || notes}
    <h3>Preview:</h3>
    <p>
      Child: {childName || "—"}  
      Mood: {mood}  
      Activities: {activities || "—"}  
      Notes: {notes || "—"}
    </p>
  {/if}
</div>
