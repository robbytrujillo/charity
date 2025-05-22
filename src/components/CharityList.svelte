<script>
    export let charities;
</script>

<div>
    <h2>Daftar Charity</h2>
    {#if charities !== undefined}
        <!-- <pre>{charities}</pre> -->
        <ul>
            {#each charities as charity}
            <!-- <li>Charity 1</li> -->
            <li>{charity.title} - {charity.category}</li>
            <!-- <li>Charity 2</li> -->
            {/each}
        </ul>
    {:else}
        <h5>Data belum tersedia</h5>
    {/if}
</div>