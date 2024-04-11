<script>
	import Home from './lib/Pages/Home.svelte';
  import {Route,Router} from 'svelte-routing'
  import RestaurantSearch from './lib/Pages/RestaurantSearch.svelte';
  import Navbar from './lib/Components/Navbar.svelte';
  // import AnimationTest from './lib/Pages/AnimationTest.svelte';
  
</script>

<Router>
  <Navbar/>
  <Route path='/' component={Home}/>
  <Route path='/restaurant' component={RestaurantSearch} />
  <!-- <Route path='/animation' component={AnimationTest} /> -->
</Router>
