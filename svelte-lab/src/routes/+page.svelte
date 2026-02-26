<script>
    import Hero from "./Hero.svelte";
    import Cards from "./Cards.svelte";
    import '../app.scss';
	  import Gallery from "./Gallery.svelte";
</script>

<Hero/>
<Cards/>
<Gallery/>


<style lang="scss">
  $primaryBlack: #0f0f0f;

  :global(html, body) {
    margin: 0;
    padding: 0;
    background-color: $primaryBlack;
  }
</style>