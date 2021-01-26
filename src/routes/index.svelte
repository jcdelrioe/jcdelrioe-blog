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
  <meta name="description" content="Blog de delrioe live" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:site" content="@jcdelrioe" />
  <meta name="twitter:creator" content="@jcdelrioe" />
  <meta name="twitter:title" content="Juan Carlos Del Rio" />
  <meta name="twitter:description" content="Blog de delrioe live" />
  <meta
    name="twitter:image"
    content="https://arepa.s3.amazonaws.com/blogpost-cover.png"
  />

  <meta name="og:title" content="Juan Carlos Del Rio" />
  <meta name="og:description" content="Blog de delrioe live" />
  <meta
    name="og:image"
    content="https://arepa.s3.amazonaws.com/blogpost-cover.png"
  />
  <meta name="og:url" content="https://blog.delrioe.live" />
  <meta name="og:site_name" content="Juan Carlos Del Rio" />
  <meta name="og:locale" content="es_ES" />
  <meta name="og:type" content="article" />
  <meta name="fb:app_id" content="" />
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
