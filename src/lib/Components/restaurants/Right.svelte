<script>
    export let restaurantData
    console.log(restaurantData);
</script>




<div class="rightsection w-[30vw] h-[90vh] overflow-y-scroll  bg-[#161616]">
    <h2 class="text-white text-xl text-center m-5">MENU</h2>
    <ul>
        {#each Object.keys(restaurantData) as key}
        {#if key === 'Menu'}
            {#each restaurantData[key] as menuItem}
                <li class="text-white flex p-6 bg-[#1e1e1e] m-3 justify-between">
                    <p>{menuItem}</p>
                    <p>$850</p>
                </li>
            {/each}
        {/if}
    {/each}
  </ul>
</div>