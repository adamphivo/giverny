<script>
  import anime from "animejs/lib/anime.es";

  function enter(e) {
    anime({
      targets: "#cursor",
      scale: 5,
    });
  }
  // Decrease size of Cursor and Hamburger
  function leave(e) {
    anime({
      targets: "#cursor",
      scale: 1,
    });
  }
</script>

<div class="logo" on:mouseenter={enter} on:mouseleave={leave}>
  <img src="/images/logo.svg" alt="logo" />
  <p></p>
</div>

<style>
  .logo {
    background-color: rgb(78, 202, 119);
    width: 90px;
    height: 90px;
    cursor: pointer;
    position: relative;
  }

  .logo img {
    width: 60px;
    height: 60px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
</style>
