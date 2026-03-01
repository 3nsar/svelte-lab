<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
import 'font-awesome/css/font-awesome.min.css';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
