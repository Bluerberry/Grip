<script>
	import { url } from '@roxi/routify'
</script>

<style>
	.centered {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100%;
	}

	h1, p {
		color: black;
		margin: 0px;
	}

	h1 {
		font-size: 12rem;
	}
</style>

<div class="centered">
	<h1> 404 </h1>
	<p> Page not found. <a href={$url('../')}>Go back</a></p>
</div>
