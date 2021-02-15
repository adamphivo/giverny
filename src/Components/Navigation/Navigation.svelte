<script>
  import Logo from "./Logo.svelte";
  import Hamburger from "./Hamburger.svelte";
  import Language from "./Language.svelte";
  import Icons from "./Icons.svelte";
</script>

<nav>
  <Logo />
  <Hamburger />
  <Language />
  <Icons />
</nav>
<style>
  nav {
    height: 100%;
    display:flex;
    flex-direction: column;
  }
</style>
