<script>
	import CharityList from "../components/CharityList.svelte";
    import { charities } from "../data/charities.js";

	let title = "Charity";
	
	// definisikan state apa yang mau dikirimkan
	// let charities = [
	// 	'Charity 1',
	// 	'Charity 2',
	// 	'Charity 3',
    //     'Charity 4',
    //     'Charity 5'
	// ];
</script>

<style>
    h1 {
        font-size: 3em;
        color: #e2071c;
    }	

    /* :global(div) { */
    /* div {
        border: 0.5em solid #1a1a1a;
        padding: 1em;
    } */
</style>

<!-- <svelte:head>
	<link rel="stylesheet" href="https://cdn.rawgit.com/kimeiga/bahunya/css/bahunya-0.1.3.css">
</svelte:head> -->

<div>
	<h1>{title}</h1>
	<CharityList {charities} />
    <!-- <CharityList /> -->
</div>