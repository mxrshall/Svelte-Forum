<script>

import { createEventDispatcher } from 'svelte';

let dispatch = createEventDispatcher();

let nazov
let kategoria
let prispevok

const onSubmit = () => {
    const info = {
        nazov: nazov,
        kategoria: kategoria,
        text: prispevok,
        id: Math.random() 
    }

    dispatch("addInfo", info)
}


</script>

<form on:submit|preventDefault={onSubmit}>
    <input type="text" placeholder="Nazov prispevku" bind:value={nazov}>
    <select id="kategoria" name="kategoria">
        <option value={kategoria}>Sport</option>
        <option value="Zabava">Zabava</option>
        <option value="Ine">Ine</option>
    </select>
    <input type="text" placeholder="Príspevok" bind:value={prispevok}>
    <button>Pridat prispevok</button>
</form>


<style>

form{
    margin-top: 20px;
}


</style>