<script>
  import anime from "animejs/lib/anime.es";

  function enter(e) {
    anime({
      targets: "#cursor",
      scale: 4,
    });
  }
  // Decrease size of Cursor and Hamburger
  function leave(e) {
    anime({
      targets: "#icon",
      scale: 1,
    });
    anime({
      targets: "#cursor",
      scale: 1,
    });
  }
</script>

<div id="icons">
  <i
    class="fal fa-ticket-alt fa-lg"
    on:mouseenter={enter}
    on:mouseleave={leave}
  />
  <i
    class="far fa-shopping-bag fa-lg"
    on:mouseenter={enter}
    on:mouseleave={leave}
  />
  <i
    class="fal fa-envelope fa-lg"
    on:mouseenter={enter}
    on:mouseleave={leave}
  />
  <i
    class="fal fa-info-circle fa-lg"
    on:mouseenter={enter}
    on:mouseleave={leave}
  />
</div>

<style>
  #icons {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
    max-height: 366px;
    margin-left: auto;
    margin-right: auto;
  }

  #icons i {
    border-top: #434b9c 2px solid;
    margin-top: 22px;
    padding-top: 22px;
    color: #434b9c;
    cursor: pointer;
  }

  i:last-child {
    border-bottom: #434b9c 2px solid;
    padding-bottom: 20px;
    color: white;
  }
</style>
