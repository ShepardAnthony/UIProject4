<script>
  let count = 0
  const donate = () => {
    if(count > 0){
      let message = 'Thank you for donating $' + count + ' to ' + charity.name
      alert(message) 
      count = 0
    }
  }

  export let charity = {};
</script>


<main>
  <div class="charity-card">
    <h2 style="padding-top:10px;">{charity.name}</h2>
    <img class="logo" src={charity.image} alt="{charity.name} logo"/>
    <p style="font-size: 20px; margin-bottom:3px;">Donation Amount:</p>
    <div class="donoContainer">
      <span class='dono prefix'>$</span>
      <input type="number" id="dono amount" class="dono input" bind:value={count}>
      <span class='dono suffix'>USD</span>
    </div>
    <button on:click={donate} class='dono-button'>
      {#if count > 0}
        Donate ${count} to {charity.name}
      {:else}
        Donate to {charity.name}
      {/if}

    </button>
  </div>
</main>


<style>
  .charity-card{
    background-color: #4B8378;
    margin:5%;
    place-items:center;
    border-radius: 25px;
  }
  .dono-button{
    margin-bottom: 10px;
    color: white;
    background-color: #FF9636;
  }
  .dono-button:active{
    background-color:#c27228;
  }
  .input{
    margin-bottom: 0px;
    padding: 6px;
    font-weight: 500;
    font-size:20px;
    background-color: white;
    border: 2px solid #E4D7D0;
  }
  .dono{
    height: 35px;
    font-size: 20px;
    line-height: 21px;
    color:#0A4158;
  }
  .prefix{
    padding: 6px 15px;
    font-weight: 400;
  }
  .suffix{
    font-weight: 500;
    padding: 6px 15px;
    padding-left:3px;
    text-align: center;
    border-left: none;
    white-space: nowrap;
  }
  .donoContainer{
    background-color: #E4D7D0;
    margin-bottom: 10px;
  }
  .logo{
    height:auto;
    width:95%;
  }
</style> 

