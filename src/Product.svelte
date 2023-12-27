<script>
    import {createEventDispatcher} from 'svelte';
    export let title;
    export let price
    export let bestseller = false;
    export let id;
    const dispatch = createEventDispatcher()

    function addToCard() {
        dispatch('add-to-card', {id: 'p1'});
    }
</script>

<article>
    <h1>{title}</h1>
    <h2>${price}</h2>
    <h3>id:{id}</h3>
    <button on:click="{addToCard}">Add to Card</button>
    <button on:click="{() => dispatch('delete', 'p1')}">Delete</button>
</article>