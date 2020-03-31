<script>
	let name = ""
	let tempC = 20
	$: tempF = Math.round(tempC * 1.8 + 32)
</script>

<h1>Hot Chocolate</h1>
<h3>with Github</h3>
<h5>clone without .git</h5>
<label>
	Name:
	<input type="text" bind:value={name}>
</label>

<label>
	Drink temperature:
	<input type="range" min="0" max="100" bind:value={tempC}>
</label>

{#if name.length > 0}
	<p>Hi {name}, your drink is {tempC} degrees. ({tempF} degrees Fahrenheit).</p>

	{#if tempC < 40}
		... fairly tepid
	{:else if tempC > 90}
		... very hot!!!
	{:else}
		... looking really good
	{/if}
{/if}

