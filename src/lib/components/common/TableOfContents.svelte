<script lang="ts">
	import { page } from '$app/state';
	import classNames from 'classnames';

	interface Props {
		project?: string;
		tableOfContents: {
			title: string;
			slug?: string;
		}[];
	}

	const { tableOfContents, project }: Props = $props();
	function isActive(pathname: string) {
		return page.url.pathname === pathname;
	}
</script>

<aside
	class="hidden h-[calc(100vh-88.67px)] w-[300px] flex-col space-y-3 overflow-y-auto border-r border-gray-900 py-5 pl-5 text-gray-400 md:flex"
>
	{#each tableOfContents as metadata}
		{@const pathname = project
			? metadata.slug
				? `/docs/${project}/${metadata.slug}`
				: `/docs/${project}`
			: metadata.slug
				? `/${metadata.slug}`
				: `/`}
		<a href={pathname}>
			<span
				class={classNames('transition-all ease-in-out', {
					'text-white': isActive(pathname)
				})}>{metadata.title}</span
			>
		</a>
	{/each}
</aside>
