<script>
    import Header from '../components/Header.svelte';
    import Footer from '../components/Footer.svelte';
</script>

<style>
	.content {
        flex: 1;
        margin-top: 5.063rem;
		background-color: #FFF8F0;
	}
</style>

<Header />
<div class="content">
    <slot />
</div>
<Footer />