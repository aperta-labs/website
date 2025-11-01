<script lang="ts">
	import '../../app.css';
	import '@fontsource/silkscreen';
	import '@fontsource/geist-sans';
	import '@fontsource-variable/geist-mono';
	import favicon from '$lib/assets/favicon.svg';
	import Header from '$lib/components/common/Header.svelte';
	import { HeaderType } from '$lib/enum/headerType';
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>
<Header type={HeaderType.NORMAL} />
<main class="mx-auto box-content max-w-4xl px-5">
	{@render children?.()}
</main>
<footer class="border-t border-gray-900 py-5">
	<div class="flex items-center justify-center">
		<p class="text-sm text-white">
			<span class="silkscreen uppercase">Aperta</span>
			© {new Date().getFullYear()}
		</p>
	</div>
</footer>
