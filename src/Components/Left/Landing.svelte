<script>
  import anime from "animejs/lib/anime.es";

  function enter(e) {
    anime({
      targets: "#cursor",
      scale: 20,
    });
    anime({
      targets: ".buy",
      translateX: [0, 150],
      opacity: 0,
    });
    anime({
      targets: ".secondary",
      translateX: [-150,60],
      opacity: 1,
    });
  }

  function leave(e) {
    anime({
      targets: "#cursor",
      scale: 1,
    });
    anime({
      targets: ".buy",
      translateX: [150, 0],
      opacity: 1,
    });
    anime({
      targets: ".secondary",
      translateX: [0, -150],
      opacity: 0,
    });
  }

  function zoom(e) {
    let cursor = document.querySelector("#cursor");
    cursor.style.background = "red";
    anime({
      targets: "#cursor",
      scale: 30,
    });
  }
  function dezoom(e) {
    let cursor = document.querySelector("#cursor");
    cursor.style.background = "blue";
    anime({
      targets: "#cursor",
      scale: 1,
    });
  }
</script>

<div class="landing" id="landing">
  <p class="intro">En ce moment</p>
  <div class="title" on:mouseenter={zoom} on:mouseleave={dezoom}>
    <p class="top">Plein air.</p>
    <p class="bot">De Corot à Monet</p>
  </div>
  <p class="date">
    du 27 mars au 28 juin 2020
  </p>
  <div class="tickets" on:mouseenter={enter} on:mouseleave={leave}>
    <p class="buy">Tickets</p>
    <p class="secondary">Tickets</p>
  </div>
  <div class="social">
    <i class="fab fa-facebook-f fa-lg" />
    <i class="fab fa-twitter fa-lg" />
    <i class="fab fa-instagram fa-lg" />
  </div>
</div>

<style>
  #landing {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: start;
    max-width: 100%;
    /* height: calc(100vh - 40px);
     */
     height: 100vh;
    padding-top: 180px;
    padding-left: 60px;
    color: white;
    box-sizing: border-box;
  }
  @media (max-width: 1250px) {
    #landing {
      padding-top: 90px;
    }
  }
  .intro {
    max-width: 142px;
    /* background-color: white; */
    color: white;
    font-family: "Museo Sans Rounded 500";
    /* font-style: italic; */
    font-size: 18px;
    line-height: 21px;
    border-radius: 5px;
    z-index: 2;
    text-transform: uppercase;
  }

  .title {
    margin-top: 20px;
    font-family: "Museo 900";
    font-size: 80px;
    width: 1000px;
    line-height: 90px;
    position: relative;
    text-transform: uppercase;
    cursor: pointer;
    word-break: keep-all;
    z-index: 2;
  }

  .top {
    color: white;
    z-index: 3;
    word-break: keep-all;
  }

  .bot {
    position: relative;
    z-index: 1;
  }

  .date {
    margin-top: 20px;
    font-family: "Museo Sans Rounded 500";
    font-size: 22px;
    text-transform: uppercase;
    border-bottom: 1px solid white;
  }

  .date i {
    margin-right: 20px;
  }

  .tickets {
    cursor: pointer;
    position: relative;
    width: 300px;
  }

  .secondary {
    position: absolute;
    top: 48px;
    left: -65px;
    font-family: "Museo Sans Rounded 500";
    font-size: 120px;
    opacity:0;
    text-transform: uppercase;
  }

  .buy {
    font-family: "Museo Sans Rounded 500";
    width: 50%;
    letter-spacing: 1px;
    z-index: 2;
    position: relative;
    margin-top: 50px;
    font-size: 120px;
    cursor: pointer;
    text-transform: uppercase;
    font-weight: 900;
    -webkit-text-stroke: 1px white;
    color: transparent;
  }

  .social {
    font-family: "Museo Sans Rounded 500";
    margin-top: 50px;
    position: absolute;
    bottom: 30px;
    left: 65px;
  }

  .social i {
    margin-right: 22px;
    cursor: pointer;
  }
</style>
