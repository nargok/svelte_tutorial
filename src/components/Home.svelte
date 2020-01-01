<script>
  import { link } from 'svelte-spa-router';
	import Nested from './Nested.svelte';
	import Numbers from './Numbers.svelte';
	import Login from './Login.svelte';

	export let name;
	let food = "orange";
	const string = `this string contains some <strong>HTML!!!</strong>`;
	let count = 0;
	$: doubled = count * 2;

	function hdandleClick() {
		count += 1;
	}

	$: if (count >= 10) {
		alert(`count is dangerously high!`);
		count = 9;
	}

</script>


<main>
	<h1>Hello {food}</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	<p class="paragraph">this is paragraph.</p>
	<Nested />
	<p>{string}</p>
	<p>{@html string}</p>

	<button on:click={hdandleClick}>
		Clicked { count } { count === 1 ? 'time' : 'times' }
	</button>
	<p>{ count } doubled is { doubled }</p>
	<Numbers />
	<Login />

  <div>
    <p>
      <a href="/cats" use:link>
        link to cat page
      </a>
    </p>
  </div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	.paragraph {
		color: purple;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>