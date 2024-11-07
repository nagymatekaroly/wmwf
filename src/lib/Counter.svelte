<script>
  let count = $state(0)
  const increment = () => {
    count += 1
  }
  const imagePath = '/images/my-image.jpg'; // Cseréld le a megfelelő útvonalra
</script>

<button onclick={increment}>
  count is {count}
</button>
