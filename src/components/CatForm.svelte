<script>
  import Cats from './Cats.svelte';

  let id;
  let name;

  let cats = [
		{ id: 'J---aiyznGQ', name: 'Keyboard Cat' },
		{ id: 'z_AbfPXTKms', name: 'Maru' },
		{ id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat' }
  ];
  
  function addCat(){
    const cat = {
      id,
      name,
    }
    cats = [...cats, cat]
    id = '';
    name = '';
  }
</script>

<div>
  <h2>The Famous Cats of YouTube</h2>

  <input type="text" bind:value={id} placeholder="youtube id"> 
  <input type="text" bind:value={name} placeholder="cat name">
  <button on:click={addCat}>追加</button>
  <Cats cats={cats} />
</div>