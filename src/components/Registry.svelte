<script>
	import ExternalLinkIcon from './ExternalLinkIcon.svelte';
</script>

<div class="registryBox">
	<div>
		Your presence is all that is required! However, if you want to give something, we have three
		options:
		<ul>
			<li>
				On account of having a fairly small and very well stocked apartment, there aren't many
				physical items we are wanting for, but we've collated some into a registry you can access
				at <a
					href="https://docs.google.com/spreadsheets/d/1uMRYOgCUU9Jx-n6tYc0xLPfgog_xFtmBiGk1jHZzp7s/edit?usp=sharing"
					target="_blank"
					rel="noreferrer">this spreadsheet <ExternalLinkIcon /></a
				>;
			</li>
			<li>
				If you're down to give to charity, we think <a
					href="https://www.givedirectly.org"
					target="_blank"
					rel="noreferrer">givedirectly.org <ExternalLinkIcon /></a
				>
				does a good job;
			</li>
			<li>Finally, we're doing a wishing well if you'd like to chip in for our honeymoon.</li>
		</ul>
	</div>
</div>

<style>
	.registryBox {
		max-width: 550px;
		margin: auto;
	}

	.registryBox div, .registryBox li {
		margin-bottom: 15px;
	}

	h1 {
		font-family: 'Architects Daughter';
	}
</style>
