<script>
  // Kép elérési útja
  const imagePath1 = 'murloc.png';
  const imagePath2 = 'Démonpanda.jpg';
  const imagePath3 = 'Monji.jpg';
  const imagePath4 = 'Vynlos.jpg';
  const imagePath5 = 'Vaelahyr.jpg';
  const imagePath6 = 'Ronyszkusz.jpg';
  const napPath = 'nap.png';
  const holdPath = 'hold.png'
  
  let sound= new Audio('mMurlocAggroOld.ogg')
  
  function playSound() {
    sound.play();
  }

import { onMount } from 'svelte';

let theme = 'light';

onMount(() => {
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme) {
        theme = savedTheme;
        document.documentElement.setAttribute('data-theme', theme);
    }
});

function toggleTheme() {
    theme = theme === 'light' ? 'dark' : 'light';
    document.documentElement.setAttribute('data-theme', theme);
    localStorage.setItem('theme', theme);
}

</script>





<header>
  <div>
    World Murlok Wrestling Federation
  </div>

  <button on:click={toggleTheme} aria-label="Toggle theme" >
    {#if theme == 'light'}
      <img id='img' src={napPath} alt="nap" />
    {:else}
    <img id='img' src={holdPath} alt="hold" />        
    {/if}
</button>
  
  <div>
    <!-- svelte-ignore a11y_img_redundant_alt -->
    <!-- svelte-ignore a11y_click_events_have_key_events -->
    <!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
    <img id='murlok' src={imagePath1} alt="Clickable Image" on:click={playSound} />
  </div>

</header>




<main>  
  
  <div id='rcorners1'>
    <img src={imagePath2} alt="Démonpanda" />
    <h2>Démonpanda-Silvermoon</h2>
    <!-- svelte-ignore a11y_missing_attribute -->
    <a>
      Tank Demon Hunter. 
      <br>Nem a legjobb tank de legalább van.
    </a>
  </div>
  

  <div id='rcorners1'>
    <img src={imagePath3} alt="Monji" />
    <h3>Monji-Ragnaros</h3>

    <!-- svelte-ignore a11y_missing_attribute -->
    <a>
      Monk healer. 
      <br>A csapat egyik új tagja. 
      <br>Jelmondata: "Az istenit.".
    </a>
  </div>

  <div id='rcorners1'>
    <img src={imagePath4} alt="Vynlos" />
    <h4>Vynlos-Ragnaros</h4>
    <!-- svelte-ignore a11y_missing_attribute -->
    <a>
      Fire Mage, ex mythic raider, mindene a logok és a számok.
      <br>Jelmondata: "Ezt még le szimelem."
    </a>
  </div>

  <div id='rcorners1'>
    <img src={imagePath5} alt="Vaelahyr" />
    <h5>Vaelahyr-Ragnaros</h5>
    <!-- svelte-ignore a11y_missing_attribute -->
    <a>
      Destruction Warlock.
      <br>Szolid játékos, erőssége a: "Ne fárasszál voltál már itt."
    </a>
  </div>

  <div id='rcorners1'>
    <img src={imagePath6} alt="Ronyszkusz" />
    <h6>Ronyszkusz-Silvermoon</h6>
    <!-- svelte-ignore a11y_missing_attribute -->
    <a>
       Retribution Paladin.
      <br>Tapasztalt Mythic+ játékos, egy hibája van túlzottan precíz.
    </a>
  </div>
  
</main>


<style>
  img {
    max-width: 10%; 
    height: auto;
    display: block; 
    margin: 0; 
    text-align: right;
    margin: 5px 5px;
  }
  

</style>