<script lang="ts">
	import { HeaderType } from '$lib/enum/headerType';
	import GithubIcon from '../icons/GithubIcon.svelte';
	import LinkedinIcon from '../icons/LinkedinIcon.svelte';
	import classNames from 'classnames';

	interface Props {
		type: HeaderType;
	}

	let { type }: Props = $props();
</script>

<div class="flex justify-center border-b border-gray-900 px-5 py-7">
	<nav
		class={classNames('flex w-full justify-between', {
			'max-w-4xl': type == HeaderType.NORMAL,
			'max-w-7xl': type == HeaderType.DOCS
		})}
	>
		<a href="/">
			<span class="silkscreen text-2xl text-white uppercase">Aperta</span>
		</a>
		<div class="flex items-center space-x-3">
			<GithubIcon />
			<LinkedinIcon />
		</div>
	</nav>
</div>
