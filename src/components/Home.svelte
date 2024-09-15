<script setup lang="ts">
	import WavingMitchAndRachel from './WavingMitchAndRachel.svelte';
</script>

<div class="home">
	<div class="padding-lg">
		<WavingMitchAndRachel />
	</div>
	<div class="homeBox">
		<div>
			<div>Heyyoooo, it's Mitch and Rachel (and Birby).</div>
			<div>We're getting married, come join us!</div>
		</div>
	</div>
</div>

<style>
	.padding-lg {
		padding: 25px;
	}

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
