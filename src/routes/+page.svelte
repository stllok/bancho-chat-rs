<div class="grid h-screen grid-cols-4">
	<div class="m-3 flex flex-col gap-3 self-baseline">
		{#each [123, 321, '+'] as e}
			<button class="rounded-full border-2 bg-gray-100 p-3 text-center hover:bg-gray-400"
				>{e}</button
			>
		{/each}
	</div>
	<div class="col-span-3 grid grid-rows-10 bg-white">
		<div class="row-span-9 flex flex-col bg-gray-400">
			<p>test: hello world!</p>
			<p>test: XD</p>
		</div>
		<div class="flex">
			<input type="text" class="grow bg-gray-500 text-2xl" />
			<button class="bg-green-500 px-5">{'=>'}</button>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.purple.800);
	}
</style>
