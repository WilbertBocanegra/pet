<script>
	import { onMount } from 'svelte';
	/**
	 * @type {HTMLIFrameElement}
	 */
	let component;
	onMount(() => {
		console.log(component.contentDocument);
		console.log('login', component.contentDocument?.cookie);
	});
</script>

<h1>PET</h1>
<iframe src="https://two-wilbertbocanegra.vercel.app" title="login app" bind:this={component} />
