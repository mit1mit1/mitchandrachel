<script>
	import ExternalLinkIcon from './ExternalLinkIcon.svelte';
</script>

<div class="RSVPBox">
	<div>
		Please RSVP with the form below. If it doesn't load you can use <a
			rel="noreferrer"
			target="_blank"
			href="https://docs.google.com/forms/d/e/1FAIpQLSfsjA0psK_P3OJLfxAZ1m4AtLnIWEKuGRYPk4Xn02oUasfqpg/viewform?usp=sf_link"
			>this link <ExternalLinkIcon /></a
		>.
	</div>
	<div>
		If you have any questions or details you need to let us know about, or just don't want to use a
		Google form, feel free to contact us directly.
	</div>
</div>
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

<style>
	.RSVPBox {
		max-width: 550px;
		margin: auto;
	}

	.RSVPBox div {
		margin-bottom: 15px;
	}
</style>
