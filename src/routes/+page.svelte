<script setup lang="ts">
	import { projectList } from '../constants/projects';
</script>

<h1>Projects by mit1mit1</h1>
{#each projectList as project}
	<div class="projectBox">
		<h2>{project.name}</h2>
		{#if project.description}
			<div>{project.description}</div>
		{/if}
		<div>
			<a href={project.githubAddress}>GitHub</a>
		</div>
		{#if project.siteAddress}
			<div>
				<a href={project.siteAddress}>Site</a>
			</div>
		{/if}
	</div>
{/each}

<style>
	.clickable {
		cursor: pointer;
		font-weight: bold;
	}
</style>
