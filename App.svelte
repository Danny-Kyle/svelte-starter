<!--First lesson: First Component -->
<script>
	const name = 'Svelte';
</script>

<h1>Hello {name.toUpperCase()}!</h1>

<!--Second lesson: Dynamic Attributes-->
<script>
	let src = '/image.gif';
	const name = 'Rick Astley';
</script>

<img {src} alt="{name} dances." />

<!--Third Lesson: Styling-->
<p>This is a paragraph.</p>

<style>
	p {
		color: goldenrod;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>

<!-- Fourth Lesson: Nested Components -->
<script>
	import Nested from './Nested.svelte';
</script>

<p>This is a paragraph.</p>
<Nested />

<style>
	p {
		color: goldenrod;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>
