<script>
  export let entries = {};
  let photo = "";

  function handleFile(e) {
    const file = e.target.files[0];
    if (file) {
      const reader = new FileReader();
      reader.onload = () => {
        photo = reader.result;
        entries.photoMemory = { photo };
      };
      reader.readAsDataURL(file);
    }
  }
</script>

<div class="card" style="background:#ffe0b2;">
  <h2>Photo / Memory</h2>
  <input type="file" accept="image/*,video/*" on:change={handleFile} />
  {#if photo}
    <p>Preview:</p>
    <img src={photo} alt="memory" style="max-width:100%; border-radius:8px;" />
  {/if}
</div>
