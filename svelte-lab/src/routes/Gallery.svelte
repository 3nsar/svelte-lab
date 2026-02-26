<script lang="ts">
	import { onMount } from 'svelte';

	type Quote = {
		id: number;
		quote: string;
		author: string;
	};

	type ApiResponse = {
		quotes: Quote[];
	};

	let quotes = $state<Quote[]>([]);
	let currentIndex = $state(0);

	onMount(async () => {
		const res = await fetch('https://dummyjson.com/quotes');
		const data: ApiResponse = await res.json();
		quotes = data.quotes;
	});

	function nextQuote() {
		currentIndex++;
	}
</script>

<div class="container">
	<div class="quotes">
		<p>"{quotes[currentIndex]?.quote}"</p>
		<p>— {quotes[currentIndex]?.author}</p>


	

	<button class="button-common" onclick={nextQuote}>
		Next Quote
	</button>
        </div>
</div>

<style lang="scss">
    .quotes{
        width: 100%;
        max-width: 1200px;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        p{
            font-size: 20px;
        }
        button{
            margin-top: 40px;
        }
    }
</style>