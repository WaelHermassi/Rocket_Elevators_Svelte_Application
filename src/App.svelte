<script>
import Header from "./components/Header.svelte";
import Footer from "./components/Footer.svelte";
</script>
<svelte:head>
  
</svelte:head>
<Header/>
<main>
	<div id="definition"><h2>Definition</h2></div>
	<p> A non-fungible token (NFT) is a non-interchangeable unit of data stored on a blockchain, a form of digital ledger, that can be sold and traded.[1] Types of NFT data units may be associated with digital files such as photos, videos, and audio. Because each token is uniquely identifiable, NFTs differ from most cryptocurrencies, such as Bitcoin, which are fungible.
		NFT ledgers claim to provide a public certificate of authenticity or proof of ownership, but the legal rights conveyed by an NFT can be uncertain. NFTs do not restrict the sharing or copying of the underlying digital files, do not necessarily convey the copyright of the digital files, and do not prevent the creation of NFTs with identical associated files.
		NFTs have been used as a speculative asset, and they have drawn increasing criticism for the energy cost and carbon footprint associated with validating blockchain transactions as well as their frequent use in art scams.[2] The NFT market has also been compared to a Ponzi scheme.</p>	
	
	<div id="uses"><h2>Uses</h2></div>
	<p>NFTs have been used to exchange digital tokens that link to a digital file asset. Ownership of an NFT is often associated with a license to use such a linked digital asset, but generally does not confer copyright to the buyer. Some agreements only grant a license for personal, non-commercial use, while other licenses also allow commercial use of the underlying digital asset.<br>
		-Digital art <br>
		-Games <br>
		-Music<br>
		-Film<br>
		-Speculation<br>
		-Money laundering<br>
	</p>
</main>
<Footer/>
<style>
	main {
		text-align: justify;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	#definition{
		position: relative;
		margin-left: 0%;
	}
	#uses{
		position: relative;
		margin-left: 0%;
	}
	h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
		margin-left: 0%;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>