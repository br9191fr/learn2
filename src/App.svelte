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
    let showModal = false;
    let closeable = false;

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
<button on:click={() => showModal = true}>Show Modal</button>

{#if showModal}
    <Modal
    on:cancel={() => showModal = false}
    on:close={() => showModal = false}
    let:didAgree={closeable}
    >
        <h1 slot="header">Hello !</h1>
        <h2>Bruno</h2>
        <button slot="footer" on:click={() => showModal = false} disabled={!closeable}>Confirm</button>
    </Modal>
{/if}
