<script>
  let username = "Parent";
  let startTime = Date.now();
  let now = new Date();

  $: duration = Math.floor((Date.now() - startTime) / 1000);
</script>

<!-- <div class="card" style="margin-bottom:1rem; text-align:center; background:#ffe5ec;">
  <h1>🌸 Little Moments</h1>
  <p>User: {username}</p>
  <p>Date: {now.toLocaleDateString()} | Time: {now.toLocaleTimeString()}</p>
  <p>Session: {duration} seconds</p>
</div> -->



<div class="card" style="margin-bottom:1.5rem; text-align:center; background:#ffe5ec;">
  <h1>🌸 Little Moments</h1>
  <p style="margin:0.5rem 0;">User: {username}</p>
  <p>{now.toLocaleDateString()} | {now.toLocaleTimeString()}</p>
  <p>Session: {duration} seconds</p>
</div>
