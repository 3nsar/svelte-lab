<script>
    import Hero from "./Hero.svelte";
    import Cards from "./Cards.svelte";
    import '../app.scss';
	import Info from "./Info.svelte";

</script>

<Hero/>
<Info/>
<Cards/>



<style lang="scss">
  $primaryBlack: #0f0f0f;

  :global(html, body) {
    margin: 0;
    padding: 0;
    background-color: $primaryBlack;
  }
</style>