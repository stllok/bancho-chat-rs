<script lang="ts">
	function formatDate(date: Date) {
		let month = '' + (date.getMonth() + 1);
		let day = '' + date.getDate();
		let year = date.getFullYear();
		let hour = date.getHours();
		let min = date.getMinutes();
		let sec = date.getSeconds();

		if (month.length < 2) month = '0' + month;
		if (day.length < 2) day = '0' + day;

		return [year, month, day].join('-') + ' ' + [hour, min, sec].join(':');
	}
	interface Message {
		time: Date;
		user: string;
		context: string;
	}
	const CHANNEL = ['#osu', '#chinese', 'BanchoBot', '+'];
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
	<div class="flex flex-row bg-gray-600">
		{#each CHANNEL as msg}
			<p class="text-whit1 rounded-t-2xl border-2 border-purple-600 bg-purple-400 p-2">{msg}</p>
		{/each}
	</div>
	<div class="flex flex-grow flex-col bg-gray-400">
		{#each TEST_MSG as msg}
			<p>[{formatDate(msg.time)}] {msg.user}: {msg.context}</p>
		{/each}
	</div>
	<div class="flex">
		<input type="text" class="grow bg-gray-500 text-2xl" />
		<button class="bg-green-500 px-5">{'=>'}</button>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.purple.800);
	}
</style>
