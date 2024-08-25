<script setup lang="ts">
	import WavingMitchAndRachel from './WavingMitchAndRachel.svelte';
</script>

<div class="home">
	<WavingMitchAndRachel />
	<div class="homeBox">
		<div>
			<div>Yo it's Mitch and Raaaachel.</div>
			<div>We're pretty cool.</div>
			<div>Come watch us get married.</div>
		</div>
	</div>
</div>

<style>
	.home {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.home div {
		margin-bottom: 15px;
	}

	.homeBox {
		display: flex;
		vertical-align: top;
		max-width: 520px;
	}
</style>
