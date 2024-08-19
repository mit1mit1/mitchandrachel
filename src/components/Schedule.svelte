<script setup lang="ts">
	import Pizza from './Pizza.svelte';
	import Rings from './Rings.svelte';
	import Saxaphone from './Saxaphone.svelte';
</script>

<div class="scheduleBox">
	<div class="scheduleText">
		<h4>Ceremony</h4>
		<div>11am</div>
		<Rings />
	</div>
	<div class="scheduleText">
		<h4>Lunch</h4>
		<div>1pm</div>
		<Pizza />
	</div>
	<div class="scheduleText">
		<h4>Speeches / Jams</h4>
		<div>2pm - Late</div>
		<Saxaphone />
	</div>
</div>

<style>
	.scheduleBox {
		display: flex;
		flex-wrap: wrap;
		gap: 2em;
		width: 100%;
		justify-content: center;
	}

	.scheduleBox div {
		margin-bottom: 15px;
	}

	.scheduleText {
		display: inline-block;
		vertical-align: top;
		text-align: center;
	}
</style>
