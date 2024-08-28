<script lang="ts">
	import Schedule from '../components/Schedule.svelte';
	import RSVP from '../components/RSVP.svelte';
	import Home from '../components/Home.svelte';
	import Registry from '../components/Registry.svelte';
	import AuthenticationProvider from '../components/AuthenticationProvider.svelte';
	const tabs = ['Schedule', 'Registry', 'RSVP'];
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
					<button on:click={() => selectTab(tab)} class={tab === selectedTab ? 'selectedTab' : ''}>
						{#if tab === selectedTab && expandedContainer === false}
							<i class="fa-solid fa-bars phoneOnly buttonIcon" />
						{/if}
						{tab}
					</button>
				{/each}
			</div>
			<div style="display: contents">
				<div class="pageContainer">
					{#if selectedTab === 'Schedule'}
						<Home />
						<Schedule />
					{:else if selectedTab === 'Registry'}
						<Registry />
					{:else if selectedTab === 'RSVP'}
						<RSVP />
					{/if}
				</div>
			</div>
		</div>
	</AuthenticationProvider>
</body>

<style>
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

	.navContainer button {
		margin-bottom: 5px;
		transition-duration: 0.4s;
		border: none;
		padding: 8px 12px;
		width: 100%;
		font-size: 1.15em;
		font-family: 'Quicksand', sans-serif;
		cursor: pointer;
		color: black;
		min-height: 50px;
		overflow: hidden;
		transition: max-height 0.5s ease-out;
		display: none;
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

	.navContainer button:hover {
		background-color: #c4c3c3;
	}

	.navContainer .selectedTab {
		background-color: #d7d7d7;
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
		background-color: rgba(240, 240, 240, 0.93);
		margin-block: 20px;
		border-radius: 10px;
		max-width: 800px;
		margin-inline: auto;
		padding: 20px;
		min-height: calc(100vh - 20px);
	}

	.app {
		margin: 0px;
		/* background-color: #1fc8db; */
		/* background-image: linear-gradient(140deg, #eadedb 0%, #bc70a4 50%, #bfd641 75%); */
		background-image: url('./suzarosa.svg');
		background-position: center; /* Center the image */
		background-repeat: no-repeat; /* Do not repeat the image */
		background-size: cover; /* Resize the background image to cover the entire container */
		background-attachment: fixed;
		font-family: 'Quicksand', sans-serif;
	}
</style>
