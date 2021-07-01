<script>
    import {onMount} from "svelte";
    let series = [];
    onMount(async function(){
        const response = await fetch('https://raw.githubusercontent.com/StreamCo/react-coding-challenge/master/feed/sample.json');
        const data = await response.json();
        series = data.entries;
        console.log(series);
    })
</script>

<main>
    <div class="series">
        {#each series as card}
        {#if card.programType === 'series'}
        <div class="card">
            <div class="img">
                <img  height="500px" src={card["images"]["Poster Art"]["url"]} alt="img">
            </div>
            <p>{card.title}</p>
        </div>
        {/if}
        {/each}
    </div>
</main>

<style>
    .series{
        display: grid;
        grid-template-columns: 30% 30% 30%;
        justify-content: center;
        align-items: center;
    }
    .card{
        margin:10px;
        box-shadow: 1px 1px 1px 1px grey;
        border-radius: 2px;
    }
    .img img{
        width:100%;
    }
    .card p{
        text-align: center;
        font-size: 20px;
        font-weight: 700;
    }
</style>