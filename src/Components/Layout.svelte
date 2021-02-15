<script>
  import Navigation from "./Navigation/Navigation.svelte";
  import Landing from "./Left/Landing.svelte";
  import anime from "animejs/lib/anime.es";

  function enter(e) {
    anime({
      targets: "#cursor",
      scale: 10,
    });
    anime({
      targets: '#info',
      opacity: 1,
    })
    document.querySelector('#cursor').innerHTML = "";
    let cursor = document.querySelector('#cursor');
    cursor.style.opacity = 1;
    cursor.style.background = "rgba(12,12,222,1)";
    cursor.style.mixBlendMode = "difference";
  }

  function leave(e) {
    let cursor = document.querySelector('#cursor');
    cursor.style.background = "red";
    anime({
      targets: "#cursor",
      scale: 1,
    });
    anime({
      targets: '#info',
      opacity: 0,
    })
    document.querySelector('#cursor').innerHTML = "";
    cursor.style.mixBlendMode = "difference";
  }
</script>

<div id="layout">
  <div id="navigation">
    <Navigation />
  </div>
  <div id="left">
    <Landing />
  </div>
  <div id="right">
    <div id="background" on:mouseenter={enter} on:mouseleave={leave}>
      <div id="info">
        <!-- <img src="/images/monet1.jpg" alt="test" class="thumbnail"/> -->
        <p>Camille Corot Trouville, bateaux de pêche échoués dans le canal, entre 1848 et 1875 © RMN-Grand Palais (musée du Louvre) / Hervé Lewandowski</p>
      </div>
    </div>
  </div>
</div>

<style>
  #layout {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    height: auto;
    width: 100%;
  }

  #navigation {
    background-color: rgb(255, 255, 255);
    height: 100%;
    min-height: 100%;
    box-sizing: border-box;
    width: 90px;
  }

  #left {
    background-color: #434b9c;
    height: 100%;
    width: calc(50% - 45px);
  }

  #right {
    background-color: white;
    height: 100%;
    width: calc(50% - 45px);
  }


  #background {
    width: 100%;
    /* height: calc(100vh - 40px); */
    height: 100vh;
    position: relative;
    background-image: url("/images/monet1.jpg");
    background-position: center center;
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    cursor: none;
  }

  #info {
    position: absolute;
    bottom: 0;
    left: 0;
    opacity: 0;
    height: auto;
    padding: 10px;
    width: 100%;
    background-color: rgba(255, 255, 255, 0.363);
    display: flex;
    flex-direction: row;
    justify-content: start;
    align-items: center;
    backdrop-filter: blur(10px);
    opacity: 0;
  }

  #info p {
    width: 80%;
    color: #434B9C;
    font-family: 'Museo Sans 500';
    font-size: 14px;
    line-height: 17px;
    margin-left: 20px;
  }

  .thumbnail {
    width: 80px;
    margin-right: 20px;
    height: auto;
  }
</style>
