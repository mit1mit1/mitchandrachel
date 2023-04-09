<script setup lang="ts">
	import WavingMe from './WavingMe.svelte';
</script>

<h1>About me</h1>
<div class="aboutMeBox">
	<WavingMe />
	<div class="aboutMeText">
		<div>Hi there! I'm Mitch. I like beanies.</div>
		<div>
			I have 6 years experience building apps for administration and finance. I mostly work in
			Typescript/NodeJS, React and Python.
		</div>
		<div>
			When I'm not working on those, I dabble in music and math flavoured projects as an excuse to
			try out new languages and frameworks.
		</div>
		<div>
			When I'm not working on <i>those</i>, I enjoy actually playing music, reading philosophy and
			fantasy, and board-gaming.
		</div>
	</div>
</div>

<style>
	.aboutMeBox {
		display: flex;
	}

	.aboutMeBox div {
		margin-bottom: 15px;
	}

	.aboutMeText {
		display: inline-block;
		vertical-align: top;
		max-width: 520px;
	}
</style>
