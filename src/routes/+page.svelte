<script setup lang="ts">
	import { projectList } from '../constants/projects';
</script>

<div class="pageContainer">
	<h1>Projects by mit1mit1</h1>
	{#each projectList as project}
		<div class="projectBox">
			<h2>
				{#if project.iconFilename}
					<img class="boxIcon" src={project.iconFilename} alt={`Picture of ${project.name}`} />
				{/if}
				{#if project.siteAddress}
					<a href={project.siteAddress}>{project.name}</a>
				{:else}
					{project.name}
				{/if}
			</h2>
			<div>
				Github: <a href={project.githubAddress}>{project.githubAddress}</a>
			</div>
			{#if project.description}
				<div>{project.description}</div>
			{/if}
		</div>
	{/each}
</div>

<style>
	.projectBox {
		max-width: 550px;
	}

	.pageContainer {
		max-width: 900px;
		margin-left: auto;
		margin-right: auto;
		font-family: Quicksand;
	}
	.pageContainer h1 {
		font-family: 'Architects Daughter';
	}

	.projectBox h2 {
		font-family: 'Indie Flower';
		margin-bottom: 5px;
	}

	.projectBox div {
		margin-bottom: 5px;
	}
	
	.boxIcon {
		max-width: 40px;
		max-height: 40px;
		vertical-align: bottom
	}
</style>
