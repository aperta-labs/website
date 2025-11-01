<script module>
	import { Link } from '@lucide/svelte';
	export { h1, h2, h3 };
</script>

<script lang="ts">
	import type { Snippet } from 'svelte';
</script>

{#snippet linkage(title: string, snippet: Snippet)}
	<div
		class="not-prose group mb-3 flex items-center space-x-3"
		id={title.toLowerCase().replaceAll(' ', '-')}
	>
		{@render snippet()}
		<button
			class="cursor-pointer text-white opacity-0 transition ease-in-out group-hover:opacity-100"
		>
			<Link size={15} />
		</button>
	</div>
{/snippet}

{#snippet h1(title: string)}
	{#snippet content()}
		<h1 class="text-2xl text-white">{title}</h1>
	{/snippet}
	{@render linkage(title, content)}
{/snippet}

{#snippet h2(title: string)}
	{#snippet content()}
		<h2 class="text-xl text-white">{title}</h2>
	{/snippet}
	{@render linkage(title, content)}
{/snippet}

{#snippet h3(title: string)}
	{#snippet content()}
		<h3 class="text-lg text-white">{title}</h3>
	{/snippet}
	{@render linkage(title, content)}
{/snippet}
