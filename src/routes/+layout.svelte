<script lang="ts">
	import '../app.css';
	import '@fontsource/silkscreen';
	import '@fontsource/geist-sans';
	import '@fontsource-variable/geist-mono';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/common/Header.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<Header />
{@render children?.()}
