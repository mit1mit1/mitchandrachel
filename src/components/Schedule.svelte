<script setup lang="ts">
	import Rings from './Rings.svelte'
</script>

<div class="scheduleBox">
	<div class="scheduleText">
		<div>11am, </div>
		<div>Location: Suzarosa, 17 Berambing Crest, Berambing NSW 2758</div>
		<div>Lunch to be provided</div>
		<Rings />
	</div>
</div>

<style>
	.scheduleBox {
		display: flex;
	}

	.scheduleBox div {
		margin-bottom: 15px;
	}

	.scheduleText {
		display: inline-block;
		vertical-align: top;
		max-width: 520px;
	}
</style>
