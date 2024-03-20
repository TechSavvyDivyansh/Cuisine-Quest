<script>
    import Card from './Card.svelte'
    import indian_food from '../../../assets/indian.png'
    import Desert from '../../../assets/Desert.jpg'
    import barbequee from '../../../assets/barbequee.png'
    import Thai from '../../../assets/thai.jpg'
    import strretfood from '../../../assets/vadaPav.png'

    let dataset=[{
        "food":"INDIAN FOOD",
        "image":indian_food,
        "desc":"A tantalizing fusion of aromatic spices and vibrant flavors",
        "expanded":false,
        
    },
    {
        "food":"DESSERT",
        "image":Desert,
        "desc":"Tempting treats that promise sweet satisfaction",
        "expanded":false,
        
    },
    {
        "food":"BARBEQUEE",
        "image":barbequee,
        "desc":"A sizzling showcase of smoky, savory, and irresistible",
        "expanded":false,
        
    },
    {
        "food":"THAI",
        "image":Thai,
        "desc":"A burst of vibrant flavors, aromatic spices and exotic culinary adventure",
        "expanded":false,
        
    },
    {
        "food":"STREET FOOD",
        "image":strretfood,
        "desc":"offering spicy delights and savory sensations straight from the bustling streets of Mumbai",
        "expanded":false,
        
    }]

    let w=10
</script>

<div class="-translate-y-28">
    <p class="text-center text-white text-4xl m-8">FAVOURITE BITES</p>
    <div class="flex flex-col md:flex-row justify-between w-[70vw] m-auto">
        {#each dataset as data,i}
            <Card {data} key={i}/>
        {/each}
    </div>
</div>



