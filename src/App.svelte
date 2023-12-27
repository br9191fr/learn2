<script>
    let products = [
        {
            id: 'p1',
            title: 'A newbook',
            price: '19.99'
        }
    ];
    import Product from "./Product.svelte";

    function addToCard(event) {
        console.log(event.detail);
    }
    function deleteProduct(event) {
        console.log(event.detail);
    }
</script>
{#each products as product}
<Product title={product.title}
         price={product.price}
         on:add-to-card={addToCard}
         on:delete={deleteProduct}
/>
{/each}




