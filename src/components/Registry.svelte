<script>
	import ExternalLinkIcon from './ExternalLinkIcon.svelte';
</script>

<div class="registryBox">
	<div>
		Your presence is all that is required! However, if you want to give something, we have two
		options:
		<ul>
			<li>
				On account of having a fairly small and very well stocked apartment, there aren't many
				physical items we are wanting for, but we've collated some into a registry you can access at <a
					href="https://docs.google.com/spreadsheets/d/1uMRYOgCUU9Jx-n6tYc0xLPfgog_xFtmBiGk1jHZzp7s/edit?usp=sharing"
					target="_blank"
					rel="noreferrer">this spreadsheet <ExternalLinkIcon /></a
				>;
			</li>
			<li>
				We're doing a wishing well if you'd like to chip in for our honeymoon or a long distant
				house deposit:
				<ul>
					<li>Account name: Mitchell Roberts</li>
					<li>Account number: 22296212</li>
					<li>BSB: 728728</li>
					<li>Bank name: Summerland Bank</li>
				</ul>
			</li>
		</ul>
	</div>
</div>

<style>
	.registryBox {
		max-width: 650px;
		margin: auto;
	}

	.registryBox div,

	.registryBox li {
		margin-bottom: 15px;
	}

	.registryBox li ul {
		margin-left: 0;
		padding-left: 15px;
		margin-top: 5px;
	}

	.registryBox li ul li {
		margin-bottom: 2px;
		list-style-type: none;
		margin-left: 0;
	}

	h1 {
		font-family: 'Architects Daughter';
	}
</style>
