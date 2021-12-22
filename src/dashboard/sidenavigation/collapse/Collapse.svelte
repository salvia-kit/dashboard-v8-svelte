<script>
	import { slide } from 'svelte/transition';
	import AngleDownIcon from './AngleDownIcon.svelte';
	import AngleRightIcon from './AngleRightIcon.svelte';

	let show = false;

	const toggle = () => {
		show = !show;
	};
</script>

<div role="button" on:click={toggle} class="flex justify-start -mb-1 py-6 px-4 text-black text-sm">
	<slot name="item" />
	<span class="ml-auto">
		<span hidden={!show}>
			<AngleDownIcon />
		</span>
		<span hidden={show}>
			<AngleRightIcon />
		</span>
	</span>
</div>
{#if show}
	<div transition:slide class="overflow-hidden text-gray-600">
		<slot name="panel" />
	</div>
{/if}
