<script>
    import Header from '../components/Header.svelte';
    import Footer from '../components/Footer.svelte';
</script>

<style>
	.content {
        flex: 1;
        width: 75%;
        margin-top: 5.063rem;
        padding: 90px 0px;
	}
</style>

<Header />
<div class="content">
    <slot />
</div>
<Footer />