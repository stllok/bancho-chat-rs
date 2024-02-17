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

	export let datetime: Date;
	export let username: string;
</script>

<div class="flex gap-1">
	<p>[{formatDate(datetime)}]</p>
	<p>{username}:</p>
	<p><slot /></p>
</div>
