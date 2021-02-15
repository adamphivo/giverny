<script>
  import anime from "animejs/lib/anime.es";

  export let language = "fr";
  export let secondary = "en";

  function switchLanguage(){
    [language, secondary ] = [secondary,language];
  }

  function change(e) {
    anime({
      targets: "#before",
      opacity: 1,
      translateX: [-150, 0],
    });
    anime({
      targets: "#main",
      opacity: 1,
      translateX: [0, 150],
    });
    anime({
      targets: "#cursor",
      scale: 6,
    });
  }
  
  function normal(e) {
    anime({
      targets: "#before",
      opacity: 0,
      translateX: [0, 150],
    });
    anime({
      targets: "#main",
      opacity: 1,
      translateX: [-150, 0],
    });
    anime({
      targets: "#cursor",
      scale: 1,
    });
  }
</script>

<div id="language-selector" 
  on:mouseenter={change} 
  on:mouseleave={normal}
  on:click={switchLanguage}
>
  <p id="before">{secondary}</p>
  <p id="main">{language}</p>
</div>

<style>
  div {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 90px;
    height: 90px;
    cursor: pointer;
    color: #434b9c;
  }
  p {
    font-family: 'Museo 900';
    font-weight: 900;
    text-align: center;
    font-size: 20px;
    line-height: 24px;
    text-transform: uppercase;
  }
  
  #before {
    opacity: 0;
    position: absolute;
    top: 32px;
    left: 32px;
  }
</style>
