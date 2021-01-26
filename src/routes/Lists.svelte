<script>
	const getData = (async () => {
			const data = await fetch("http://localhost:5000/api/v1/lists");
			const response = await data.json();
			return response;
	})();
</script>

{#await getData}
	<div>fetching data ...</div>
{:then lists}
	<ul>
		{#each lists.data as {id, lists_name}, i}
			<li>{i + 1}: {lists_name}</li>
		{/each}
	</ul>

{:catch error}
	<div>{error}</div>
{/await}

