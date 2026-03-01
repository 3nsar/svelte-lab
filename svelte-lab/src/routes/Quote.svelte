<script lang="ts">
	import { onMount } from 'svelte';
    import { goto } from '$app/navigation';

  function goToHome() {
    goto('/');
  }

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
    {#if quotes.length > 0}
      <p>"{quotes[currentIndex]?.quote}"</p>
      <p>— {quotes[currentIndex]?.author}</p>
    {:else}
      <div class="spinner"></div>
    {/if}
		<button class="button-common" onclick={nextQuote}>
		Next Quote
	</button>

	   <button class="button-common button-back" onclick={goToHome}>Go Back</button> 
  </div>
</div>

<style lang="scss">
@import '../app.scss';
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
	.button-back{
		background-color: $primaryLightBlack;
	}
.spinner {
  width: 40px;
  height: 40px;
  border: 4px solid $primaryGray;
  border-top: 4px solid $primaryBlue;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

</style>