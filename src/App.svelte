<script>
    let value;
    let inputField
    let valueList = []


    function handleBtn() {

        valueList = [...valueList, value];
        inputField.value = '';
    }

    function onDelete(id) {
        valueList.splice(id, 1);
        valueList = valueList;
    }

</script>
<main>
    <input type="text" bind:this={inputField} bind:value={value}>
    <button on:click={handleBtn}>Add todo</button>
    {#each valueList as value,i}
        <p> {value}
            <button style="color: red"  on:click={()=>onDelete(i)}>x</button>
        </p>
    {/each}
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
