<script>
    import Hero from "./Hero.svelte";
    import Cards from "./Cards.svelte";
   import '../app.scss';
</script>

<Hero/>
<Cards/>


<style lang="scss">
  $primaryBlack: #0f0f0f;

  :global(html, body) {
    margin: 0;
    padding: 0;
    background-color: $primaryBlack;
  }
</style>