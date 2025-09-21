<script>
  import Header from './components/Header.svelte';
  import Feeding from './components/Feeding.svelte';
  import Diaper from './components/Diaper.svelte';
  import Sleep from './components/Sleep.svelte';
  import Firsts from './components/Firsts.svelte';
  import PhotoMemory from './components/PhotoMemory.svelte';
  import HealthVaccine from './components/HealthVaccine.svelte';
  import Growth from './components/Growth.svelte';

  let entries = {};

  function saveData() {
    localStorage.setItem("littleMoments", JSON.stringify(entries));
    alert("Entries saved locally!");
  }
</script>

<Header />

<div class="container">
  <div class="grid">
    <Feeding bind:entries />
    <Diaper bind:entries />
    <Sleep bind:entries />
    <Firsts bind:entries />
    <PhotoMemory bind:entries />
    <HealthVaccine bind:entries />
    <Growth bind:entries />
  </div>

  <div style="text-align:center; margin-top: 1.5rem;">
    <button on:click={saveData}>Save Entries</button>
  </div>
</div>
