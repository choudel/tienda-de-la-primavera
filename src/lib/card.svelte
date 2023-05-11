<script lang="ts">
  import { fragment, graphql } from "$houdini";

  /* @type { import('$houdini').SpriteInfo } */
  export let item;
  //ts-ignore
  $: stuff = fragment(
    item,
    graphql(`
      fragment itemInfo on Item {
        items(first: 4) @paginate {
          nodes {
            id
            nodeId
            item
            price
            sellText
          }
        }
      }
    `)
  );
  $: console.log($stuff.items.nodes[0]);
</script>

{#each $stuff.items.nodes as node}
  <div class="card">
    <div class="item-pic">
      <img src="bag-mini.png" alt="bag" />
    </div>
    <div class="label">
      <div class="item-name">{node.item}</div>
      <div class="sell-text">{node.sellText}</div>
      <div class="price">{node.price} D.A</div>
    </div>
  </div>
{/each}
<slot />

<style lang="scss">
  img {
    max-width: 20vw;
    height: auto;
  }
</style>
