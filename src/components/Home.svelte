<script setup lang="ts">
	import gandalfAndFrodo from '../img/gandalfAndFrodo.jpg';
</script>

<div class="home">
	<div class="padding-lg">
		<img src={gandalfAndFrodo} alt="flag" width="250px" />
	</div>
	<div class="homeBox">
		<div>
			<div>Hey friends and fam -</div>
			<div>We're getting married, and we'd love you to join us!</div>
		</div>
	</div>
</div>

<style>
	.padding-lg {
		padding: 25px;
	}

	.home {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.home div {
		margin-bottom: 15px;
	}

	.homeBox {
		display: flex;
		vertical-align: top;
		max-width: 650px;
	}
</style>
