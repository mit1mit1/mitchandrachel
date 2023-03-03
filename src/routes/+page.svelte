<script lang="ts">
	import Projects from '../components/Projects.svelte';
	import SupportUs from '../components/SupportUs.svelte';
	import AboutMe from '../components/AboutMe.svelte';
	import Contact from '../components/Contact.svelte';
	const tabs = ['About me', 'Projects', 'Contact', 'Support us'];
	let selectedTab = 'About me';

	const selectTab = (tab: string) => {
		selectedTab = tab;
	};
</script>

<body class="app" data-sveltekit-preload-data="hover">
	<div style="display: contents">
		<div class="pageContainer">
			<div class="navContainer">
				{#each tabs as tab}
					<button on:click={() => selectTab(tab)} class={tab === selectedTab ? 'selectedTab' : ''}
						>{tab}</button
					>
				{/each}
			</div>
			{#if selectedTab === 'About me'}
				<AboutMe />
			{:else if selectedTab === 'Projects'}
				<Projects />
			{:else if selectedTab === 'Support us'}
				<SupportUs />
			{:else if selectedTab === 'Contact'}
				<Contact />
			{/if}
		</div>
	</div>
</body>

<style>
	.navContainer {
		max-width: 900px;
		list-style-type: none;
		margin: 0;
		padding: 0;
	}
	@media (min-width: 500px) {
		.navContainer {
			display: flex;
    	justify-content: space-evenly;
		}
	}

	.navContainer button {
		margin-right: 2px;
		margin-bottom: 5px;
		transition-duration: 0.4s;
		border: none;
		padding: 8px 12px;
		min-height: 40px;
		width: 100%;
		font-size: 0.95em;
		font-family: 'Quicksand', sans-serif;
		cursor: pointer;
	}

	.navContainer button:hover {
		background-color: #c4c3c3;
	}

	.navContainer .selectedTab {
		background-color: #d7d7d7;
	}

	.pageContainer {
		margin-left: 10px;
		margin-right: 10px;
		font-family: Quicksand;
	}
	@media (max-width: 640px) {
		.pageContainer {
			width: 100%;
			margin-left: 0px;
			margin-right: 0px;
		}
	}
	@media (max-width: 270px) {
		.pageContainer {
			overflow-wrap: anywhere;
		}
	}

	.app {
		background-color: #f8f8f8;
		min-height: 100%;
	}
</style>
