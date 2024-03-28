<script>
    import { onMount } from "svelte";
    import { apiData, drinkNames } from '../../stores/store';

    const delay = () => {
    return new Promise(resolve => setTimeout(resolve, 2000));
    };

    $: listLength = $drinkNames.length;

    onMount(async () => {

        const dl = await delay()
        const res = await fetch("https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=Bourbon")
        .then(response => response.json())
        .then(data => {
                console.log(data);
            apiData.set(data);
        }).catch(error => {
            console.log(error);
            return [];
        });
        });

</script>


{#if listLength != 0}
<h1>Whiskey Drinks Menu</h1>
<ul>
{#each $drinkNames as drinkName}
    <li>{drinkName}</li>
{/each}
</ul>
{:else}
<p>Waiting</p>
{/if}
