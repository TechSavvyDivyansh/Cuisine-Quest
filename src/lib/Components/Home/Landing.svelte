<script>
    import restaurant from '../../../assets/restaurant.png'
    import {Link} from 'svelte-routing'
</script>

<div class="">
    <img src={restaurant} alt="" class="absolute top-10 h-[50vh] md:h-auto md:top-0 xl:-top-72 -z-10 w-[100vw] opacity-[16%]">
    <div class="text w-[100vw] h-[100vh] flex flex-col gap-5 md:gap-16 items-center m-auto justify-center p-7">
        <div class="flex flex-col items-center gap-4">
            <p class="text-[#FABF68] text-xl md:text-6xl tracking-[8px] md:tracking-[28px] w-[100vw] text-center">Taste the Goodness</p>
            <p class="text-[#F3D482] text-sm md:text-3xl font-light tracking-[4px]">LOVE THE EXPERIENCE</p>
        </div>
        <p class="text-white tracking-[2px] w-[50vw] text-center text-xs md:text-lg">Discover top-notch eateries registered with us! From cozy cafes to  upscale bistros, each promises an unforgettable dining experience. Come,  taste excellence today!</p>
        <button class="px-7 py-2 text-black bg-[#FABF68]"><Link to='/restaurant'>EXPLORE MORE</Link></button>
    </div>
</div>
