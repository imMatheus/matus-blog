<script lang="ts" context="module">
	export async function load(context: any) {
		const res = await fetch('https://jsonplaceholder.typicode.com/posts');
		const posts = await res.json();

		if (res.ok) {
			return {
				props: {
					posts
				}
			};
		}

		return {
			status: res.status,
			error: new Error('Could not fetch the guides')
		};
	}
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
