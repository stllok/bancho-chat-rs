<script lang="ts">
	import ChannelTab from '$lib/ChannelTab.svelte';
	import MessageContext from './MessageContext.svelte';

	let current_channel = '#osu';
	let channels = ['#osu', '#chinese', 'BanchoBot'];

	interface Message {
		time: Date;
		user: string;
		context: string;
	}
	const TEST_MSG: Message[] = [
		{
			time: new Date(1565605570 * 1000),
			user: 'Player1',
			context: 'Hello world!'
		},
		{
			time: new Date(1565605595 * 1000),
			user: 'Player2',
			context: 'Hello world!'
		},
		{
			time: new Date(1565605670 * 1000),
			user: 'Player3',
			context: 'Hello world!'
		}
	];
</script>

<div class="flex h-screen flex-col">
	<div class="flex flex-row bg-purple-800">
		{#each channels as channel}
			<ChannelTab name={channel} bind:current_channel bind:channels></ChannelTab>
		{/each}
		<ChannelTab bind:current_channel bind:channels></ChannelTab>
	</div>
	<div class="flex flex-grow flex-col bg-gray-400">
		{#each TEST_MSG as msg}
			<MessageContext datetime={msg.time} username={msg.user}>{msg.context}</MessageContext>
		{/each}
	</div>
	<div class="flex">
		<input type="text" class="grow bg-gray-500 p-2 text-2xl" placeholder="Input message here" />
		<button class="bg-green-500 px-5">{'=>'}</button>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.purple.800);
	}
</style>
