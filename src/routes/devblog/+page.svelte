<script>


  /** @type {import('./$types').PageData} */
  export let data;
</script>

<article>
  <h1>Blog</h1>
  
  <ul>
    {#each data.posts as post}
      <li>
        <h2>
          <a href={"/devblog/" + post.path}>
            {post.meta.title}
          </a>
        </h2>
        Published {post.meta.date}
      </li>
    {/each}
  </ul>

  
<style>

  article{
    background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
  }
</style>

</article>
