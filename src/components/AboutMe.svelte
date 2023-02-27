<script setup lang="ts">
	import WavingMe from './WavingMe.svelte';
</script>

<h1>About me</h1>
<div class="aboutMeBox">
    <WavingMe />
    <div class="aboutMeText">
        <div>This  - is, me.</div>
        <div>I think it’s apparent I need to rethink my life a little bit.</div>
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
