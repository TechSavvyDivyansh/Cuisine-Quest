<script>
	import { Link,navigate } from 'svelte-routing';
	import { onMount } from 'svelte';
    import { fly } from 'svelte/transition'
    
    let animateNav=false 


    onMount(()=>{
        animateNav=true
    })

    let Search=''

    let urlParams=new URLSearchParams(location.search)
    let searchQuery=urlParams.toString()
    $:{
        urlParams.set('searchTerm',Search)
        searchQuery=urlParams.toString()
    }

    $:openMenu=false

    const toggleMenu=()=>{
        openMenu=!openMenu
    }

    let handleSearch=(e)=>{
        e.preventDefault()
        navigate(`/restaurant?${searchQuery}`)
    }
    

</script>

 
{#if animateNav}
    <header class='bg-[rgba(0,0,0,1)] md:bg-transparent absolute w-[100vw] flex flex-col md:flex-row items-center px-5 py-2 md:p-7 md:px-20 gap-5 md:justify-between shadow-xl'
            transition:fly={{y:-150,duration:1000}}>
        <!-- LOGO+ open close menu icon -->
        <div class="flex items-center justify-between w-[90vw] md:w-auto translate-y-3">
            <span class="text-[#FABF68] md:text-xl lg:text-2xl font-normal">Cuisine Quest</span>
            <div class="icons md:hidden">
            <button on:click={toggleMenu}><i class='bx bx-menu-alt-right text-white text-xl' hidden={openMenu}/></button>
            <button on:click={toggleMenu}><i class='bx bxl-xing text-white text-xl' hidden={!openMenu}/></button>
            </div>
        </div>

        <form class="flex bg-[rgba(255,255,255,0.4)] text-white">
            <input type="text" bind:value={Search} placeholder="SEARCH..." class={openMenu?"text-center  placeholder:text-white md:w-[20vw] outline-none py-1 rounded-sm":"hidden md:block text-center bg-[rgba(255,255,255,0.1)] text-white placeholder:text-white w-[20vw] outline-none py-1 rounded-sm"}>
            <button class="p-2 text-center" on:click={handleSearch}><i class='bx bx-search'></i></button>
        </form>

        <!-- navigation links -->
        <div class={openMenu?"":"hidden md:inline"}>
            <ul class='flex flex-col md:flex-row items-center gap-3 md:gap-4 lg:gap-16'>
                <li class='text-white font-normal cursor-pointer md:text-base lg:text-lg hover:text-gray-400 transition'><Link to='/'>HOME</Link></li>
                <li class='text-white font-normal cursor-pointer md:text-base lg:text-lg hover:text-gray-400 transition'>RESTAURANTS</li>
                <li class='text-white font-normal cursor-pointer md:text-base lg:text-lg hover:text-gray-400 transition'>CUISINES</li>
            </ul>
        </div>
    </header>
{/if}