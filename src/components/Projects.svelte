<script setup lang="ts">
	import { projectList } from '../constants/projects';
	import { prettifyAddress } from '../utils/stringManipulation';
	import { assets, base } from '$app/paths';
</script>

<h1>Projects by mit1mit1</h1>
{#each projectList as project}
	<div class="projectBox">
		<h2>
			{#if project.iconName}
				{#if project.siteAddress}
					<a href={project.siteAddress} target="_blank">
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
				<a href={project.siteAddress} target="_blank">{project.name}</a>
			{:else}
				{project.name}
			{/if}
		</h2>
		<div class="detailsBox">
			<div>
				Github: <a href={project.githubAddress} target="_blank"
					>{prettifyAddress(project.githubAddress)}</a
				>
			</div>
			{#if project.description}
				<div>{project.description}</div>
			{/if}
		</div>
	</div>
{/each}

<style>
	.projectBox {
		max-width: 550px;
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
		vertical-align: bottom;
	}

	h1 {
		font-family: 'Architects Daughter';
	}

    .detailsBox {
        padding: 5px;
        margin: 5px;
    }
</style>
