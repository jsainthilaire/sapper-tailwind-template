<script>
	export let segment;
</script>

<style>
	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}
</style>

<nav class="py-0 px-4 font-light border border-solid border-red-600 border-opacity-25">
	<ul class="m-0 p-0">
		<li class="block float-left"><a class="block px-4 py-2 no-underline" aria-current="{segment === undefined ? 'page' : undefined}" href=".">home</a></li>
		<li class="block float-left"><a class="block px-4 py-2 no-underline" aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
		<li class="block float-left"><a class="block px-4 py-2 no-underline" rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li>
	</ul>
</nav>
