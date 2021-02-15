<script>
  import anime from "animejs/lib/anime.es";

  // Increase size of Cursor and Hamburger
  function enter(e) {
    anime({
      targets: "#icon",
      scale: 1.2,
    });
    anime({
      targets: "#cursor",
      scale: 2,
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

<div id="hamburger" 
  on:mouseenter={enter} 
  on:mouseleave={leave}>
  <i class="fal fa-bars fa-2x" id="icon" />
</div>

<style>
  #hamburger {
    position: relative;
    /* border-top: 2px solid white; */
    color: white;
    width: 90px;
    height: 90px;
    background-color: #384099;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }
</style>
