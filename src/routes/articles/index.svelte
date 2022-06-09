<script lang="ts" context="module">
	import type { Load } from '@sveltejs/kit';
	import fs from 'fs';
	import path from 'path';

	export const load: Load = async (context) => {
		const markdown = fs.readFileSync(path.join('../../articles/sql.md'), 'utf8');

		// console.log(__dirname);
		console.log(markdown);

		return {
			status: 200,
			error: new Error('Could not fetch the guides')
		};
	};
</script>

<script lang="ts">
	export let posts: any[];
</script>

<div class="posts">
	<ul>
		{#each posts as post}
			<li>
				<a href="/">{post.title}</a>
			</li>
		{/each}
	</ul>
</div>

<h1>About this site</h1>
<p>TODO...</p>

<a href="/">Home</a>
