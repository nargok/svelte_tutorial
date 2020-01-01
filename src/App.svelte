<script>
	import Router from 'svelte-spa-router';
	import Home from './components/Home.svelte';
	import CatForm from './components/CatForm.svelte';

  const routes = {
		'/': Home,
		'/cats/': CatForm,
	}
</script>

<div>
	<Router {routes}/>
</div>