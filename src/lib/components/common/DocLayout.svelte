<script lang="ts">
	import { page } from '$app/state';
	import { Pencil } from '@lucide/svelte';
	import type { Snippet } from 'svelte';

	interface Props {
		children: Snippet;
	}

	const { children }: Props = $props();

	function githubLocation() {
		const pathname = page.url.pathname;
		const githubUrl = `https://github.com/aperta-labs/website/tree/main/src/routes/(docs)${pathname}/+page.svx`;
		return githubUrl;
	}
</script>

<article class="h-[calc(100vh-88.67px)] w-full space-y-7 overflow-y-auto pt-5 pl-5">
	<div class="prose">
		{@render children()}
	</div>
	<div class="border-t border-gray-900">
		<a href={githubLocation()}>
			<div class="flex items-center space-x-2 py-5 text-white">
				<Pencil size={15} />
				<span>Edit this page</span>
			</div>
		</a>
	</div>
</article>
