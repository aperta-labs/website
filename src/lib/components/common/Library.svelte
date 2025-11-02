<script lang="ts">
	interface Props {
		library: {
			title: string;
			description: string;
			href: string;
		};
	}
	const { library }: Props = $props();
</script>

<a href={library.href}>
	<div
		class="not-prose h-[115px] space-y-2 rounded-lg border border-gray-900 bg-gray-950/50 p-5 shadow-sm shadow-black/50"
	>
		<h2 class="geist-mono mt-0! text-sm! text-white">{library.title}</h2>
		<p class="text-gray-400!">{library.description}</p>
	</div>
</a>
