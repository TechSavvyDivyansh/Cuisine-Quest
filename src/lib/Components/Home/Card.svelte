<script>
    import { onMount } from 'svelte'
    import { tweened } from "svelte/motion";
    import { fly } from 'svelte/transition'
    export let data
    export let key

    let tweenedwidth=tweened(10)

    let expand=()=>{
        data.expanded=true
        tweenedwidth.set(25)
    }
    let shrink=()=>{
        tweenedwidth.set(10)
        data.expanded=false
    }

    let EntryAnimation=false 
    onMount(()=>{
        EntryAnimation=true
    })

    

</script>


<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
{#if EntryAnimation}
    <div class="card flex flex-col gap-2 h-[450px]" 
    on:mouseenter={expand} 
    on:mouseleave={shrink} 
    transition:fly={{ x: -100, duration: 300, delay: key * 500 }}>

    <div class={`flex flex-col items-center justify-center cursor-pointer`}>
        <img src={data.image} alt="" class={`object-cover rounded-xl opacity-[40%]`} style="width:{$tweenedwidth}vw;height:450px">
        <p class={`text-white ${data.expanded?"":"-rotate-90"} text-3xl -translate-y-56`}>{data.food}</p>
    </div>
    {#if data.expanded}
        <div class="-translate-y-52 flex flex-col gap-2 items-center">
            <!-- <p class="text-white text-center w-[40%]">{data.desc}</p>   -->
            <button class="text-black px-3 py-1 text-center bg-[#FABF68]">ORDER NOW</button>
        </div>
    {/if}
    </div>
{/if}