<script>
	import {Router, Route} from 'svelte-routing';
	import NavLink from './components/NavLink.svelte'
	import Home from './routes/Home.svelte';
	import Lists from './routes/Lists.svelte';
	import Profile from './routes/Profile.svelte';

	export let url = "";
</script>

<main>
	<Router url="{url}">
		<nav>
			<NavLink to="/">Home</NavLink>
			<NavLink to="list">List</NavLink>
			<NavLink to="profile">Profile</NavLink>
		</nav>
		<nav>
			<Route path="/" component="{Home}"/>
			<Route path="list" component="{Lists}"/>
			<Route path="profile" component="{Profile}"/>
		</nav>
	</Router>
</main>


