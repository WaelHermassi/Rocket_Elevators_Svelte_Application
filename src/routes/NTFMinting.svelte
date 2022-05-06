<script>
import { connected, web3,walletType, selectedAccount, chainId, chainData } from 'svelte-web3'
import { defaultEvmStores } from 'svelte-web3'
import RocketTokenContract from "./RocketToken.json"
import { onMount } from 'svelte';
const disable = () => defaultEvmStores.disconnect()

defaultEvmStores.setProvider()

async()=> {
      const web3Modal = new web3Modal()
      const provider = await web3Modal.connect()
      defaultEvmStores.setProvider(provider)
      
    }
const gift = async()=> {
        fetch(`https://rocket-elevators-express-api.herokuapp.com/NFT/gift/${$selectedAccount}`)
        .then((response)=>{
        return response.json()
        }).then((data) => {
        console.log(data)
        showresult(data)
        
        })
      }
      function  showresult(res) {
        document.getElementById('legit').innerText =`${res}`
     }
  
const CONTRACT_ADDRESS = '0x4D266d91e6bf8f111f0068E8990d43093FDA1b27';
let contractInstance;
$: checkAccount = $selectedAccount || '0x0000000000000000000000000000000000000000'
$: balance = $connected ? $web3.eth.getBalance(checkAccount) : '' 

onMount(async () => {
     await defaultEvmStores.setBrowserProvider()
     contractInstance = await getContract(CONTRACT_ADDRESS)
  })
async function getContract(address) {
  const networkId = await $web3.eth.net.getId();
  const deployedNetwork = RocketTokenContract.networks[networkId];
  return new $web3.eth.Contract(
      RocketTokenContract.abi,
    deployedNetwork && deployedNetwork.address, {
      from: address,
      gas: 2000000
    }
  );
}  
 
</script>

{#if $web3.version}
<div class="buttons">
  <button class="button is-link is-light" on:click="{disable}">disconnect</button>
</div>

<div class="buttons">
  <button id="buttonlight" on:click="{gift}">Check for NTF gift</button>
</div>
{/if}
{#if $connected}

<p>
  Connected chain: chainId = {$chainId}
</p>
<p>
  Selected account: {$selectedAccount || 'not defined'}
</p>
<p>
  Wallet type: {$walletType || 'not defined'}
</p>
<p>
  chainData = {JSON.stringify($chainData)}
</p>

  
  <p>Ligibility for an NTF gift is :</p>
  <div id= "legit"></div>
  <div id="buyntf">
    Would you like to buy an NTF?
    <button id="buttonbuy" on:click="{onMount}">Yes</button>
    <button id="buttondontbuy" on:click="{disable}">No</button>
  </div>

{/if}
