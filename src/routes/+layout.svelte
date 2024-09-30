<script lang="ts">
	import '../styles/app.css'

	let { children } = $props()
</script>

<svelte:head>
	<title>Gamechanger PPBL 2024</title>
</svelte:head>

{@render children()}