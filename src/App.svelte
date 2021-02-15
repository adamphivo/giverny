<script>
  import anime from "animejs/lib/anime.es.js";
  import Cursor from "./Components/Cursor.svelte";
  import Layout from "./Components/Layout.svelte";
  function moveCursor(e) {
    anime({
      targets: "#cursor",
      top: e.clientY - 5,
      left: e.clientX - 5,
    });
  }
</script>

<main on:mousemove={moveCursor}>
  <Layout />
  <Cursor />
</main>

<style>
  main {
    width: 100%;
    height: 100%;
    background: white;
  }
</style>
