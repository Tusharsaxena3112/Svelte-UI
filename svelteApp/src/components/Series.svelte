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
                <img  height="350px" src={card["images"]["Poster Art"]["url"]} alt="img">
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
        grid-template-columns: 27% 27% 27%;
        justify-content: center;
        align-items: center;
    }
    .card{
        margin:13px;
        box-shadow: 1px 1px 1px 1px grey;
        border-radius: 2px;
        border-radius: 10px;
    }
    .card:hover{
        filter: grayscale(100%);
        transition: 0.5s;
        cursor: pointer;
    }
    .img img{
        width:100%;
        border-radius: 10px;
    }
    .card p{
        text-align: center;
        font-size: 20px;
        font-weight: 700;
    }
</style>