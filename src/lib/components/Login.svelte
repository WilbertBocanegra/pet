<script lang="ts">
	import { onMount } from 'svelte';
	export let src: string;
	let component: HTMLIFrameElement;

	onMount(() => {
		component.src = src;
		component.width = '0';
		component.height = '0';
		component.style.display = 'none';

		const contentWindow = component.contentWindow;
		const contentDocument = component.contentDocument;
		console.log('window', contentWindow?.localStorage);
		console.log('document', contentDocument?.cookie);

		component.remove();
	});
</script>

<iframe title={undefined} bind:this={component} />
