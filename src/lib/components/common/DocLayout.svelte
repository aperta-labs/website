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

<article class="w-full space-y-7 pt-5 pl-5">
	<div
		class="prose-ul:list-desc prose overflow-y-auto prose-headings:mt-0 prose-headings:mb-3 prose-headings:font-normal prose-headings:text-white prose-h1:text-2xl prose-h1:text-white prose-h2:text-xl prose-h3:text-lg prose-p:mt-0 prose-p:text-gray-400 prose-code:text-gray-400 prose-ul:mt-0 prose-ul:ml-3 prose-li:mt-0 prose-li:mb-2 prose-li:text-gray-400"
	>
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
