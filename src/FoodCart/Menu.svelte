<script>
  import Card from "./Card.svelte";
  export let items;
</script>

<div class="container">
  <div class="row">
    {#each items as item (item.id)}
      <div class="col-md-4">
        <Card {item} />
      </div>
    {/each}
  </div>
</div>
