<script lang="ts">
  import PostCard from "$lib/components/PostCard.svelte";

  export let data;
</script>

{#if data.posts.length === 0}
 <p id="issue">There seems to have been an issue retrieving the posts.</p>
{/if}

<ul>
  {#each data.posts as post}
    <li><PostCard postInfo={post} postHeight="fit-content" postWidth="100%" /></li>
  {/each}
</ul>

<style>
  ul {
    width: 100%;
    list-style: none;
    display: grid;
    grid-template: auto / 1fr;
    row-gap: 1.5rem;
  }
  p {
    margin-top: 3rem;
    font-size: var(--fs-n);
    font-style: italic;
  }
  #issue {
    margin: auto;
  }
</style>
