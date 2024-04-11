<script>
    export let restaurantData

    console.log(restaurantData);
</script>


<div class="leftsection w-[30vw] h-[90vh] bg-[#161616] p-10 overflow-y-scroll">
    <div class="flex flex-col items-center gap-4">
        <p class="text-center text-white text-xl">COMPETITORS</p>
        {#each Object.entries(restaurantData).slice(1) as [key, rest]}
            <div class="flex flex-col bg-[#1e1e1e] w-[70%] justify-between items-center cursor-pointer">
                <img src={rest.img_link} alt="" class="w-[100%]">
                <div class="p-3">
                    <p class="text-white">{rest.res_name}</p>
                </div>
            </div>
        {/each}
    </div>
</div>