<script>
    export let restaurantData
    import restaurant from '../../../assets/restaurant.png'
    console.log(restaurantData);
</script>


<div class="centersection w-[50vw] h-[90vh] bg-[#161616] flex flex-col items-center">
    <img src={restaurantData.img_link} class="w-[95%] m-8" alt="">
    <div class="flex flex-col gap-5 items-center p-3">
        <p class="text-white text-2xl">{restaurantData.res_name}</p>
        <p class="text-[#4a4949] text-center"></p>
        <!-- <p class="text-white">{restaurantData.delivery_ratings}</p> -->
        <button class="px-7 py-2 text-black bg-[#FABF68]">COMPARE</button>
    </div>
</div>