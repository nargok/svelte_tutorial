<script>
  let numbers = [1, 2, 3, 4];

  function addNumber() {
    console.log('add number')
    // numbers.push(numbers.length + 1); // これはうごかない
    numbers = [...numbers, numbers.length + 1]; // これは動く
  }

  $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<p>{ numbers.join(' + ')} = { sum }</p>
<button on:click={addNumber}>add number</button>