<script>
    import {createEventDispatcher} from "svelte";
    let dispatch = createEventDispatcher();
    export let items;
    export let activeItem;
</script>

<main>
    <div class="tabs">
        <ul>
            {#each items as item}
                <li on:click={()=>dispatch('tabChange',item)} class:active={activeItem === item}>{item}</li>
            {/each}
        </ul>
    </div>
</main>

<style>
    .tabs{
        margin:10px;
    }
    ul{
        list-style-type: none;
        display: flex;
    }
    li{
        margin:auto 6px;
        font-size: 20px;
        cursor: pointer;
        font-weight: 700;
    }
    .active{
        color:red;
        border-bottom: 1px solid red;
    }
</style>