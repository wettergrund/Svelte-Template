<script>
    import { onMount } from 'svelte';

	/** @type {import('./$types').PageData} */
	export let data;

    onMount
</script>


<h2>{data.post.title}</h2>
<p>{@html data.post.content}</p>