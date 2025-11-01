<script>
	import '../../../app.css';
	import '@fontsource/silkscreen';
	import '@fontsource/geist-sans';
	import '@fontsource-variable/geist-mono';
	import Header from '$lib/components/common/Header.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import { HeaderType } from '$lib/enum/headerType';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>
<Header type={HeaderType.DOCS} />
<main class="mx-auto max-w-7xl">
	{@render children?.()}
</main>
