<script setup lang="ts">
	import WavingMe from './WavingMe.svelte';
</script>

<h1>About me</h1>
<div class="aboutMeBox">
	<WavingMe />
	<div class="aboutMeText">
		<div>This - is, me.</div>
		<div>
			I'm an advanced mathematics major with a thesis in philosophy. I have 6 years of software
			engineering experience, starting with php and jQuery, and (thankfully) continuing with Python,
			NodeJS and React.
		</div>
		<div>
			When I'm not working with those, I dabble in game design as an excuse to use Vue, Svelte, C and a touch of Rust.
		</div>
		<div>I think it's apparent I need to rethink my life a little bit.</div>
		<div />
	</div>
</div>

<style>
	.aboutMeBox {
		max-width: 550px;
	}

	.aboutMeBox div {
		margin-bottom: 15px;
	}

	h1 {
		font-family: 'Architects Daughter';
	}

	.aboutMeText {
		display: inline-block;
		vertical-align: top;
	}
</style>
