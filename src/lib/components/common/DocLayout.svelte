<script lang="ts">
	import { page } from '$app/state';
	import { Pencil } from '@lucide/svelte';
	import type { Snippet } from 'svelte';

	interface Props {
		children: Snippet;
		editLink?: (pathname: string) => string;
	}

	const { children, editLink }: Props = $props();

	function githubLocation() {
		const pathname = page.url.pathname;
		const githubUrl = editLink?.(pathname);
		return githubUrl;
	}
</script>

<article class="h-[calc(100vh-88.67px)] w-full space-y-5 overflow-y-auto px-5 pt-5">
	<div class="prose">
		{@render children()}
	</div>
	<div class="flex items-center justify-between border-t border-gray-900 py-5 text-sm">
		{#if editLink}
			<a href={githubLocation()}>
				<div class="flex items-center space-x-2 text-white">
					<Pencil size={12} />
					<span>Edit this page</span>
				</div>
			</a>
		{:else}
			<div></div>
		{/if}
		<div class="flex items-center text-white">
			<span class="silkscreen">Aperta</span>&nbsp;
			<span>© {new Date().getFullYear()}</span>
		</div>
	</div>
</article>
