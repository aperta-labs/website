<script lang="ts">
	import DocLayout from '$lib/components/common/DocLayout.svelte';
	import TableOfContents from '$lib/components/common/TableOfContents.svelte';
	import type { LayoutProps } from '../logging copy/$types';

	const tableOfContents = [
		{
			title: 'Introduction'
		},
		{
			title: 'Getting Started',
			slug: 'getting-started'
		},
		{
			title: 'Examples',
			slug: 'examples'
		},
		{
			title: 'Changelog',
			slug: 'changelog'
		}
	];

	const { children }: LayoutProps = $props();
</script>

<div class="flex w-full">
	<TableOfContents {tableOfContents} project="pager" />
	<DocLayout>
		{@render children()}
	</DocLayout>
</div>
