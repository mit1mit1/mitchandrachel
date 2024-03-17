<script setup lang="ts">
	import WavingMitchAndRachel from './WavingMitchAndRachel.svelte';
</script>

<div class="homeBox">
	<WavingMitchAndRachel />
	<div class="homeText">
		<div>Yo it's Mitch and Raaaachel.</div>
		<div>
			We're pretty cool.
		</div>
		<div>
			Come watch us get married.
		</div>
	</div>
</div>

<style>
	.homeBox {
		display: flex;
	}

	.homeBox div {
		margin-bottom: 15px;
	}

	.homeText {
		display: inline-block;
		vertical-align: top;
		max-width: 520px;
	}
</style>
