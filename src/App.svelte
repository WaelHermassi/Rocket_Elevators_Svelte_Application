<svelte:head>
</svelte:head>
<Header/>
<!-- <main>
	
				
	
</main> -->
<Footer/>

<script>
import Header from "./components/Header.svelte";
import Footer from "./components/Footer.svelte";
import { Router, Link, Route } from "svelte-routing";
import NTFMinting from "./routes/NTFMinting.svelte";
import Portfolio from "./routes/Portfolio.svelte";
import Home from "./routes/Home.svelte";
  
	// export let url = "";
  </script>
  
  <Router >
	
	
	  <!-- <Route path="home" component="{Home}" /> -->
	  <!-- <Route path="minting" component="{NTFMinting}" />
	  <Route path="portfolio" component="{Portfolio}" /> -->
	  <Route path="/"><Home /></Route>
	  <Route path="/NTFMinting"><NTFMinting /></Route>
	  <Route path="/Portfolio"><Portfolio /></Route>
	
  </Router>