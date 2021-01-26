
<script>
	const getData = (async () => {
			const data = await fetch("https://api.github.com/users/sulthonuladib")
			const response = await data.json();
			console.log(response)
			return response;
	})();
</script>

{#await getData}
	<div>fetching data ...</div>
{:then profile}
	<ul>

			<li>{ + 1}: {profile.avatar_url}</li>

	</ul>
			<img src="{profile.avatar_url}" alt="Profile Photo"/>

{:catch error}
	<div>{error}</div>
{/await}

