<script context="module">
  export function preload() {
    return this.fetch(`blog.json`)
      .then((r) => r.json())
      .then((posts) => {
        return { posts };
      });
  }
</script>

<script>
  import Post from "../components/Post.svelte";
  export let posts;
</script>

<svelte:head>
  <title>Juan Carlos Del Rio's blog</title>
</svelte:head>

<div class="Home">
  <div class="Posts">
    {#each posts as post}
      <Post {post} />
    {/each}
  </div>
</div>

<style>
  .Posts {
    display: grid;
    grid-template-columns: 1fr;
    gap: 15px;
  }
</style>
