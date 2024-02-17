<script lang="ts">
	export let name: string | null = null;
	export let current_channel: string;
	export let channels: string[];
</script>

<button
	disabled={name === current_channel}
	on:click={(_) => (current_channel = name ?? '')}
	class="rounded-t-2xl border-2 border-purple-700 bg-purple-500 p-2 text-white hover:bg-purple-400 disabled:bg-purple-600"
	>{name !== null ? name : '+'}
	{#if name !== null}
		<button
			on:click={(_) => {
				const i = channels.indexOf(name ?? '', 0);
				
				if (channels[i] === current_channel) {
					channels[]
				}

				if (i !== -1) {
					channels.splice(i, 1);
				}
			}}
			class="p-1 hover:bg-slate-500 active:bg-slate-100">X</button
		>
	{/if}
</button>
