<script>
let msg = ""

function doFetch(event) {
  fetch('/api/counter')
  .then(response => {
    if (!response.ok) {
      throw new Error(response.status);
    }
    return response.json()
  })
  .then(data => {
    msg = data.hello + " (" + data.count + ")"
  })
  .catch((error) => {
    msg = error
  });
}
</script>

<style>
</style>

<h1>Frontend</h1>
<h2>Hello {msg}</h2>

<button on:click={doFetch}>Call the function</button>