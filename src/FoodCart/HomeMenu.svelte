<script>
  import Card from "./Card.svelte";
  import category_items from "../items/universal_items.js";

  function decorate(text) {
    text = text.replace("_", " ");
    function capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1);
    }
    return capitalizeFirstLetter(text);
  }
</script>

<div class="container">
  {#each Object.entries(category_items) as [category, items]}
    <h1>{decorate(category)}</h1>
    <div class="row">
      {#each items as item (item.id)}
        <div class="col-md-4">
          <Card {item} />
        </div>
      {/each}
    </div>
  {/each}
</div>

<style>
  h1 {
    font-family: cursive;
    position: relative;
    overflow: hidden;
    text-align: left;
  }

  h1:after {
    display: inline-block;
    content: "";
    height: 4px;
    background: rgb(185, 181, 181);
    position: absolute;
    width: 100%;
    top: 50%;
    margin-top: -2px;
    margin-left: 10px;
  }
</style>
