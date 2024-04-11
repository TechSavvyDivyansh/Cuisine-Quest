<script>
  import Center from '../Components/restaurants/Center.svelte';
  import Left from '../Components/restaurants/Left.svelte';
  import Right from '../Components/restaurants/Right.svelte';
  import {onMount} from 'svelte'
    
  let urlParams=new URLSearchParams(location.search)
  let searchTerm=urlParams.get("searchTerm")

  let completeData=[]

  onMount(() => {
      if (searchTerm) 
      {
              let fn = async () => {
                  try {
                      let res = await fetch('http://127.0.0.1:8000/analyze_sentiment/', {
                          method: "POST",
                          headers: {
                              "Content-Type": "application/json"
                          },
                          body: JSON.stringify({ query: searchTerm })
                      });
                      let data = await res.json();
                      completeData=data 
                  } catch (error) {
                      console.error("Error fetching data:", error);
                  }
              };

              fn();
      }
});
    
$:console.log(completeData);

</script>

<div class="flex gap-1 relative top-24 justify-center">
    {#if completeData.length===0}
       <p>LOADING...</p>
    {:else}
        <Left restaurantData={completeData}/>
        <Center restaurantData={completeData[1]}/>
        <Right restaurantData={completeData[1]}/>
    {/if}
</div>

