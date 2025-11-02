<script lang="ts">
	import DocLayout from '$lib/components/common/DocLayout.svelte';
	import TableOfContents from '$lib/components/common/TableOfContents.svelte';
	import type { LayoutProps } from './$types';

	const tableOfContents = [
		{
			title: 'About'
		},
		{
			title: 'Licensing',
			slug: 'licensing'
		},
		{
			title: 'Contributing',
			slug: 'contributing'
		}
	];

	const { children }: LayoutProps = $props();
</script>

<div class="flex w-full">
	<TableOfContents {tableOfContents} />
	<DocLayout>
		{@render children()}
	</DocLayout>
</div>
