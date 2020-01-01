<script>
  export let cats
</script>

<ul>
  {#each cats as cat}
    <li>
    <a target="_blank" href="https://www.youtube.com/watch?v={cat.id}">
      {cat.name}
    </a>
    </li>
  {/each}
</ul>