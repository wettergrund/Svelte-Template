<script>
    import Footer from "../components/Footer.svelte";
    import MobileNavbar from "../components/MobileNavbar.svelte";
    import Navbar from "../components/Navbar.svelte";

    $: outerWidth = 0;

    


</script>
<style lang="scss">
    @import '../style.scss';
</style>
  


<svelte:window bind:outerWidth />

{#if outerWidth > 500}
<Navbar />
{:else}
<MobileNavbar />
{/if}

<div class="mainarea">
    <slot></slot>
</div>

<Footer />


