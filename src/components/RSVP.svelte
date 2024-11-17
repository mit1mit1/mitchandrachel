<script>
	import ExternalLinkIcon from './ExternalLinkIcon.svelte';
</script>

<div class="RSVPBox">
	<div class="smallScreenOnly">
		Please RSVP using <a
			rel="noreferrer"
			target="_blank"
			href="https://docs.google.com/forms/d/e/1FAIpQLSfsjA0psK_P3OJLfxAZ1m4AtLnIWEKuGRYPk4Xn02oUasfqpg/viewform?usp=sf_link"
			>this google form <ExternalLinkIcon /></a
		>.
	</div>
	<div class="largeScreenOnly">Please RSVP with the form below.</div>
	<div class="largeScreenOnly">
		If it doesn't load you can use <a
			rel="noreferrer"
			target="_blank"
			href="https://docs.google.com/forms/d/e/1FAIpQLSfsjA0psK_P3OJLfxAZ1m4AtLnIWEKuGRYPk4Xn02oUasfqpg/viewform?usp=sf_link"
			>this link <ExternalLinkIcon /></a
		>.
	</div>
	<div>
		If you have any questions or details you need to let us know about, or just don't want to use a
		Google form, feel free to contact us directly at <a href="mailto:mitchell.roberts11@gmail.com"
			>mitchell.roberts11@gmail.com</a
		>.
	</div>
</div>
<div class="formWrapper largeScreenOnly">
	<iframe
		title="RSVP Form"
		src="https://docs.google.com/forms/d/e/1FAIpQLSfsjA0psK_P3OJLfxAZ1m4AtLnIWEKuGRYPk4Xn02oUasfqpg/viewform?embedded=true"
		width="800px"
		height="1214"
		frameborder="0"
		marginheight="0"
		marginwidth="0"
	>
		Loading…
	</iframe>
</div>

<style>
	.smallScreenOnly {
		display: none;
	}
	@media (max-width: 800px) {
		.smallScreenOnly {
			display: block;
		}
	}

	.largeScreenOnly {
		display: none;
	}
	@media (min-width: 801px) {
		.largeScreenOnly {
			display: block;
		}
	}

	.formWrapper {
		max-width: 800px;
		margin: auto;
		margin-top: 50px;
	}

	.RSVPBox {
		max-width: 650px;
		margin: auto;
	}

	.RSVPBox div {
		margin-bottom: 15px;
	}
</style>
