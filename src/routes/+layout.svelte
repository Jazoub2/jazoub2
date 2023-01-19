<script>
  import "prism-themes/themes/prism-one-dark.css";
</script>

<svelte:head>
  <link rel="stylesheet" href="/pico.min.css" />

  <style>
    nav {
      margin-left: 10%;
      margin-right: 10%;
      background-color: rgb(177, 175, 169);
    
      
    }
  </style>
</svelte:head>
<body>
<nav>
  <ul>
    <li><a href="/">Hme</a></li>
    <li><a href="/devblog">Bolg</a></li>
  </ul>
</nav>

<main class="container-fluid">
  <hr />

  <main class="container">
    <slot />
  </main>
</main>
</body>

<style>

  hr {
    height: 50px;
    background-image: url("regnbåge.png");
    background-size:100% 100%;
    

    
    
  } 

  main {
    background-color: rgb(177, 175, 169);
    background-image: url("vertikalregnbåge2.png");
    background-size:250%;
  }
  nav {
      background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
      background-size: 100% 500%;
  }
  body{
  background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
  background-size:contain
  }

</style>
