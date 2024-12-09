<script>
  import DonationCard from './lib/DonationCard.svelte'
  import charities from './assets/charities.json'


</script>

<main>
  <h1>DonoWall</h1>

  <div class="charity-wall">
    {#each charities as charity}
      <div class="card">
        <DonationCard charity={charity}/>
      </div>
    {/each}
  </div>
</main>

<style>
  .read-the-docs {
    color: #888;
  }
  .charity-wall{
    display:flex;
    width:100%;
    place-items: center;
  }
  .card{
    width: 30%;
  }
</style>
