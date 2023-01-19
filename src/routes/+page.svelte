<script>
  let clicks = 100;
  let multiplier = 1;
  let workers = [];
  let worker_multiplier = 1;

  let upgrades = [
    { cost: 500, name: "Doble", multiplier: 2, worker: 0 },
    { cost: 10, name: "Works", multiplier: 0, worker: 1 },
  ];

  function increment() {
    clicks = clicks + multiplier;
    console.log("click" + clicks);
  }
</script>

<article>
  <header>
    <div class="grid">
      {#each upgrades as upgrade,i}

        <button
          class="upgrade"
          on:click={() => {
            if (clicks >= upgrade.cost * worker_multiplier) {
              if (upgrade.multiplier) {
                multiplier = multiplier * upgrade.multiplier;
                clicks -= upgrade.cost * worker_multiplier;
              }
              if (upgrade.worker && clicks) {
                worker_multiplier = worker_multiplier * 1;
                workers = [upgrade.name, ...workers];
                /* start "clicking" every 1000 ms */
                setInterval(increment, 1000);
                clicks -= upgrade.cost;
              }
              upgrades[i].cost=upgrades[i].cost*1.1
            } else {
              alert("im the biggest bird");
            }
          }}
        >
          <span>{upgrade.name}</span>
          <span>{Math.round(upgrade.cost * worker_multiplier)}</span>
        </button>
      {/each}
    </div>
  </header>
  <div class="game">
    <button on:click={increment} class="clicker">
      <span class="clicks">{Math.round(clicks)}</span>
      <span class="pointtext">PPC: {multiplier}</span>
    </button>
  </div>
  <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">
    <button
      style="background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU); border-color:rgb(10, 10, 10); border-width: 15px; height:100px; width:200px;color:rgb(60,60,60);"
      >Dont click</button
    >
  </a>

  <footer>
    <div class="panelright">
      <div>
        <big>workers</big>
        <hr />
        <div class="shop">
          {#each workers as worker}
            <div class="worker">{worker}</div>
          {/each}
        </div>
      </div>
      <hr />
    </div>
  </footer>
</article>

<style>
  .shop {
    display: grid;
    grid-auto-flow: row; /* default */
    gap: 8px;
    grid-template-rows: repeat(3, 1fr);
    grid-template-columns: repeat(3, 1fr);
  }

  .upgrade {
    width: 100%;
    height: 100%;
    border: 12px solid rgb(26, 12, 100);
    background-color: rgb(177, 175, 169);
    background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
    background-size: cover;
    place-items: center;
    place-content: center;
    display: flex;
    flex-direction: column;
  }

  .worker {
    width: 100%;
    height: 100%;
    border: 1px solid transparent;
    background-image: url("regnbåge.png");
    background-size: 75% 100%;
    background-position: center;
    place-items: center;
    place-content: center;
    display: flex;
  }

  .game {
    height: 50vh;
    display: flex;
    flex-direction: column;
    place-items: center;
    place-content: center;
  }
  .clicker {
    clip-path: circle();
    display: flex;
    height: 100%;
    width: 100%;
    flex-direction: column;
    place-items: center;
    place-content: center;
    background-image: url("rainbowdash.png");
    background-size: 33% 110%;
    background-position: center;
  }

  .panelright {
    height: 100%;
    display: flex;
    flex-direction: column;
    gap: 16px;
    background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
    background-size: 100%;
  }

  article {
    background-image: url("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSoCYxeuLZgEngVEtml-uCk_maD60X2-5QiTQ&usqp=CAU");
    border: 25px solid transparent;
    padding: 15px;
  }

  header {
    background-size: 100% 100%;
    border: 25px solid transparent;

    padding: 15px;
    border-image: url("regnbåge.png") 30 fill;
  }
  .clicks {
    font-size: 100px;
  }

  .pointtext {
    color: brown;
    font-size: 25px;
    font-weight: bold;
  }
  footer {
    background-image: url("regnbåge.png");
    background-size: 100% 100%;
  }
</style>
