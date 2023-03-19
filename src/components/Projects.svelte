<script setup lang="ts">
	import { projectList } from '../constants/projects';
	import { prettifyAddress } from '../utils/stringManipulation';
	import { assets, base } from '$app/paths';
</script>

<h1>Projects</h1>
<div class="subheading">In decreasing order of polish</div>
<div class="projectsContainer">
	{#each projectList as project}
		<div class="projectBox">
			<h2 class="projectTitle">
				{#if project.iconName}
					{#if project.siteAddress}
						<a href={project.siteAddress} target="_blank" rel="noreferrer">
							<img
								class="boxIcon"
								src={`${base}/images/${project.iconName}`}
								alt={`Picture of ${project.name}`}
							/>
						</a>
					{:else}
						<img
							class="boxIcon"
							src={`${base}/images/${project.iconName}`}
							alt={`Picture of ${project.name}`}
						/>
					{/if}
				{/if}
				{#if project.siteAddress}
					<a href={project.siteAddress} target="_blank" rel="noreferrer">{project.name}</a>
				{:else}
					{project.name}
				{/if}
			</h2>
			<div class="detailsBox">
				{#if project.githubAddress}
					<div>
						Github: <a href={project.githubAddress} target="_blank" rel="noreferrer"
							>{prettifyAddress(project.githubAddress)}</a
						>
					</div>
				{/if}
				{#if project.description}
					<div>{project.description}</div>
				{/if}
			</div>
		</div>
	{/each}
</div>

<style>
	.projectsContainer {
		display: grid;
		gap: 10px;
		grid-template-columns: repeat(auto-fill, minmax(400px, 1fr));
	}
	@media (max-width: 400px) {
		.projectsContainer {
			grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
		}
	}

	.projectBox {
		max-width: 510px;
		padding: 5px;
		margin-right: 50px;
	}

	.projectTitle {
		font-family: 'Indie Flower';
		margin-bottom: 5px;
		margin-top: 10px;
		display: flex;
	}

	.projectTitle a {
		margin-right: 10px;
		align-items: center;
		display: flex;
	}

	.projectBox div {
		margin-bottom: 5px;
	}

	.boxIcon {
		max-width: 40px;
		max-height: 40px;
		vertical-align: bottom;
	}

	h1 {
		font-family: 'Architects Daughter';
		margin-bottom: 5px;
	}

	.detailsBox {
		padding: 5px 0px;
		margin: 5px 0px;
	}

	.subheading {
		margin-bottom: 15px;
		font-style: italic;
		font-family: 'Architects Daughter';
		font-size: 1.2em;
	}
</style>
