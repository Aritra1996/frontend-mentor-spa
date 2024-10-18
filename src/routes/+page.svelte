<script>
	import { page } from '$app/stores';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to my new<br />SvelteKit apps
	</h1>

	<ol>
		<li aria-current={$page.url.pathname === '/counter' ? 'page' : undefined}>
			<a href="/counter">Counter</a>
		</li>
		<li aria-current={$page.url.pathname === '/faq accordion' ? 'page' : undefined}>
			<a href="/faq-accordion">FAQ Accordion</a>
		</li>
	</ol>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}

	ol {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		justify-content: center;
		align-items: center;
		background: var(--background);
		background-size: contain;
	}
</style>
