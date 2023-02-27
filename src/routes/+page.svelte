<script lang="ts">
	import Projects from '../components/Projects.svelte';
	import SupportUs from '../components/SupportUs.svelte';
	import AboutMe from '../components/AboutMe.svelte';
	import Contact from '../components/Contact.svelte';
	const tabs = ['About me', 'Projects', 'Support us', 'Contact'];
	let selectedTab = 'About me';

	const selectTab = (tab: string) => {
		selectedTab = tab;
	};
</script>

<div class="pageContainer">
	<ul class="navContainer">
		{#each tabs as tab}
			<button on:click={() => selectTab(tab)} class={tab === selectedTab && 'selectedTab'}
				>{tab}</button
			>
		{/each}
	</ul>
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

<style>
	.navContainer {
		list-style-type: none;
		margin: 0;
		padding: 0;
	}

	.navContainer button {
		margin-right: 2px;
		margin-bottom: 5px;
		transition-duration: 0.4s;
		border: none;
		padding: 8px 12px;
		min-height: 40px;
		min-width: 100px;
		font-size: 0.95em;
		font-family: 'Quicksand', sans-serif;
		cursor: pointer;
	}

	.navContainer .selectedTab {
		background-color: #aaa;
	}

	.pageContainer {
		max-width: 900px;
		margin-left: 10px;
		font-family: Quicksand;
	}
</style>
