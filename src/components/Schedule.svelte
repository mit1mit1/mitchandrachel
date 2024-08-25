<script setup lang="ts">
	import Pizza from './Pizza.svelte';
	import Rings from './Rings.svelte';
	import Saxaphone from './Saxaphone.svelte';
</script>

<div class="schedule">
	<div class="scheduleBox">
		<h4>Doors Open</h4>
		<div>11:30am</div>
		<Rings />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Ceremony</h4>
		<div>12 noon</div>
		<Rings />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Celebration photos and refreshments</h4>
		<div>1pm</div>
		<Pizza />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Lunch and lawn games</h4>
		<div>1:30pm</div>
		<Pizza />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Speeches</h4>
		<div>2:30pm</div>
		<Saxaphone />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Dessert and cocktail bar</h4>
		<div>3:00pm</div>
		<Saxaphone />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Jazz on the grass</h4>
		<div>3:30pm</div>
		<Saxaphone />
	</div>
	-->
	<div class="scheduleBox">
		<h4>End of formalities</h4>
		<div>5:00pm</div>
		<Saxaphone />
	</div>
	-->
	<div class="scheduleBox">
		<h4>Informal dinner</h4>
		<div>7:00pm</div>
		<Saxaphone />
	</div>
</div>

<style>
	.schedule {
		display: flex;
		flex-wrap: wrap;
		gap: 5px;
		width: 100%;
		justify-content: center;
		align-items: center;
	}

	.schedule div {
		margin-bottom: 15px;
	}

	.scheduleBox {
		display: inline-block;
		text-align: center;
		padding: 5px;
		border-radius: 10px;
		border: rgba(0, 0, 0, 0.2) 1px dashed;

	}

	h4 {
		max-width: 150px;
		margin-bottom: 5px;
		min-height: 2.5em;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
