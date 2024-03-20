<script>
    import restaurant from '../../../assets/restaurant.png'

    let competitor=[{
        "image":restaurant,
        "name":"sky view"
    },{
        "image":restaurant,
        "name":"Candle lit"
    },{
        "image":restaurant,
        "name":"armada"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },{
        "image":restaurant,
        "name":"abcd"
    },]
</script>


<div class="leftsection w-[30vw] h-[90vh] bg-[#161616] p-10 overflow-y-scroll">
    <div class="flex flex-col gap-3">
        <p class="text-center text-white text-xl">COMPETITORS</p>
        {#each competitor as rest}
            <div class="flex bg-[#1e1e1e] p-3 justify-between items-center cursor-pointer">
                <div class=""></div>
                <p class="text-white">{rest.name}</p>
                <img src={rest.image} alt="" class="w-[6vw]">
            </div>
        {/each}
    </div>
</div>