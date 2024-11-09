<script lang="ts">
	import Schedule from '../components/Schedule.svelte';
	import RSVP from '../components/RSVP.svelte';
	import FAQ from '../components/FAQ.svelte';
	import Home from '../components/Home.svelte';
	import Registry from '../components/Registry.svelte';
	import AuthenticationProvider from '../components/AuthenticationProvider.svelte';
	
	const tabs = ['Schedule', 'Registry', 'FAQ', 'RSVP'];
	let selectedTab = 'Schedule';
	let expandedContainer = false;

	const selectTab = (tab: string) => {
		if (selectedTab === tab && expandedContainer === false) {
			expandedContainer = true;
		} else {
			expandedContainer = false;
		}
		selectedTab = tab;
	};
</script>

<body class="app" data-sveltekit-preload-data="hover">
	<AuthenticationProvider>
		<div class="contentContainer">
			
			<h1>Mitch and Rachel</h1>
			<h2>April 5th, 2025</h2>
			<h3>Suzarosa, 17 Berambing Crest, Berambing NSW 2758</h3>
			<div class={`navContainer ${expandedContainer ? 'expandedContainer' : ''}`}>
				{#each tabs as tab}
					<button
						on:click={() => selectTab(tab)}
						class={tab === selectedTab ? 'selectedTab animateUnderline' : 'animateUnderline'}
					>
						{#if tab === selectedTab && expandedContainer === false}
							<i class="fa-solid fa-bars phoneOnly buttonIcon" />
						{/if}
						<span class="">{tab}</span>
					</button>
				{/each}
			</div>
			<div style="display: contents">
				<div class="pageContainer">
					{#if selectedTab === 'Schedule'}
						<div class="fadeIn">
							<Home />
							<Schedule />
						</div>
					{:else if selectedTab === 'Registry'}
						<div class="fadeIn">
							<Registry />
						</div>
					{:else if selectedTab === 'FAQ'}
						<div class="fadeIn">
							<FAQ />
						</div>
					{:else if selectedTab === 'RSVP'}
						<div class="fadeIn">
							<RSVP />
						</div>
					{/if}
				</div>
			</div>
		</div>
		<div class="forceMargin" />
	</AuthenticationProvider>
</body>

<style>
	/* TODO figure out animations */
	.fadeIn.visible {
		visibility: visible;
		opacity: 1;
		transition: opacity 2s linear;
	}

	.fadeIn.hidden {
		visibility: hidden;
		opacity: 0;
		transition: visibility 0s 2s, opacity 2s linear;
	}

	.buttonIcon {
		float: left;
		padding-top: 2px;
	}

	@media (min-width: 500px) {
		.phoneOnly {
			display: none;
		}
	}

	:global(h1) {
		font-family: 'Great Vibes';
		display: none;
		font-weight: 400;
		font-size: 3.5rem;
		text-transform: none;
		letter-spacing: 0em;
		text-align: center;
		padding-block-start: 0.5em;
		padding-block-end: 0em;
		margin-block-end: 0em;
		margin-block: 0em;
	}
	@media (min-width: 500px) {
		:global(h1) {
			display: block;
		}
	}

	h2 {
		font-family: 'Merienda', 'Great Vibes';
		display: none;
		font-weight: 400;
		font-size: 1.25rem;
		text-transform: none;
		letter-spacing: 0em;
		text-align: center;
		padding-block-start: 0em;
		padding-block-end: 0em;
		margin-block: 0em;
	}
	@media (min-width: 500px) {
		h2 {
			display: block;
		}
	}

	h3 {
		font-family: 'Merienda', 'Great Vibes';
		display: none;
		font-weight: 400;
		font-size: 1.5rem;
		text-transform: none;
		letter-spacing: 0em;
		text-align: center;
		padding-block-start: 0.5em;
		padding-block-end: 1em;
		margin-block: 0em;
	}
	@media (min-width: 500px) {
		h3 {
			display: block;
		}
	}

	.navContainer {
		list-style-type: none;
		margin: 0;
		padding: 0;
		margin-bottom: 20px;
	}
	@media (min-width: 500px) {
		.navContainer {
			display: flex;
			justify-content: space-evenly;
			/* margin-bottom: 0px; */
		}
	}

	.animateUnderline > span {
		position: relative;
	}

	.animateUnderline:hover > span::after,
	.animateUnderline:focus > span::after,
	.selectedTab.animateUnderline > span::after {
		opacity: 1;
		transform: scaleX(1);
	}

	.animateUnderline > span::after {
		content: '';
		position: absolute;
		width: 100%;
		transform: scaleX(0);
		height: 1px;
		bottom: 0;
		left: 0;
		background-color: #714943;
		transition: transform 0.25s ease-out;
	}

	.navContainer button {
		margin-bottom: 5px;
		transition-duration: 0.4s;
		padding: 8px 12px;
		width: 100%;
		font-size: 1.15em;
		font-family: 'Quicksand', sans-serif;
		cursor: pointer;
		min-height: 50px;
		overflow: hidden;
		transition: max-height 0.5s ease-out;
		display: none;
		color: #4a2a2f;
		background-color: transparent;
		border: none;
	}
	@media (min-width: 500px) {
		.navContainer button {
			display: inline-block;
		}
	}

	.navContainer button.selectedTab {
		display: inline-block;
	}

	.navContainer.expandedContainer button {
		transition: max-height 0.5s ease-out;
		display: inline-block;
	}

	.pageContainer {
		margin-left: 18px;
		margin-right: 18px;
		font-family: Quicksand;
	}
	@media (max-width: 270px) {
		.pageContainer {
			overflow-wrap: anywhere;
		}
	}

	.contentContainer {
		background-color: #ebe2d0;
		color: #7e5451;
		max-width: 800px;
		margin-inline: auto;
		padding: 20px;
		min-height: 100vh;
	}

	.app {
		margin: 0px;
		background-image: url('./suzarosa.svg');
		background-position: center; /* Center the image */
		background-repeat: no-repeat; /* Do not repeat the image */
		background-size: cover; /* Resize the background image to cover the entire container */
		background-attachment: fixed;
		font-family: 'Quicksand', sans-serif;
	}

	.forceMargin {
		min-height: 1px;
	}

	:global(a) {
		color: rgb(110, 150, 134);
	}

	:global(a:visited) {
		color: rgb(22, 70, 69);
	}
</style>
