<script>
    import Product from "./Product.svelte";
    import Modal from "./Modal.svelte";

    let products = [
        {
            id: 'p1',
            title: 'A newbook',
            price: '19.99'
        }
    ];

    function addToCard(event) {
        console.log(event.detail);
    }

    function deleteProduct(event) {
        console.log(event.detail);
    }
</script>
{#each products as product}
    <Product {...product}
             on:add-to-card={addToCard}
             on:delete={deleteProduct}
    />
{/each}

<Modal>
 <h1>Hello</h1>
    <h2>Bruno</h2>
</Modal>


