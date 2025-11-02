<script module>
	import { Link } from '@lucide/svelte';
	import classNames from 'classnames';
	export { h1, h2, h3 };
</script>

<script lang="ts">
	import type { Snippet } from 'svelte';
</script>

{#snippet linkage(title: string, snippet: Snippet, className: string)}
	{@const id = title.toLowerCase().replaceAll(' ', '-')}
	<a href={`#${id}`}>
		<div class={classNames('group flex items-center space-x-3', className)} {id}>
			{@render snippet()}
			<button
				class="cursor-pointer text-white opacity-0 transition ease-in-out group-hover:opacity-100"
			>
				<Link size={15} />
			</button>
		</div>
	</a>
{/snippet}

{#snippet h1(title: string)}
	{#snippet content()}
		<h1 class="mt-0!">{title}</h1>
	{/snippet}
	{@render linkage(title, content, 'mt-7')}
{/snippet}

{#snippet h2(title: string)}
	{#snippet content()}
		<h2 class="mt-0!">{title}</h2>
	{/snippet}
	{@render linkage(title, content, 'mt-5')}
{/snippet}

{#snippet h3(title: string)}
	{#snippet content()}
		<h3 class="mt-0!">{title}</h3>
	{/snippet}
	{@render linkage(title, content, 'mt-4')}
{/snippet}
