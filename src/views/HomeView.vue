<script setup>
import ButtonItem from '@/components/ButtonItem.vue';
import LogoItem from '../components/LogoItem.vue';
import BannerInfo from '../components/BannerInfo.vue'
</script>

<template>
  <!-- Principal Content -->
  <section class="welcome wrapper" id="welcome">
  <!-- text -->
    <div class="text-welcome">
      <div class="content-text">
        <h1 class="title">IGLESIA<span><br>LA GRACIA DE DIOS</span>  </h1>
        <p> Nuestra programacion en vivo aquí, enseñanzas biblicas</p>
        <button-item> Ver en vivo</button-item>
      </div>
    </div>
    <!--  -->

  <!-- video -->
    <div>
      <div class="border-iframe">
        <div class="border-iframe-2">         
          <iframe class="video" src="https://streamtv.intervenhosting.net/hybrid-stream-video-widget/iglesial" width="100%" style="aspect-ratio: 16/9; min-height: 320px;" frameborder="0" scrolling="no" allow="autoplay" allowfullscreen webkitallowfullscreen mozallowfullscreen oallowfullscreen msallowfullscreen></iframe>
        </div>
      </div>
    </div>
    <!--  -->
  </section>

  <div class="wrapper">
    <div class="line "></div>
  </div>
  
  <!-- Daughters churches  -->
  <section class="churches-content wrapper" id="churches">
    <div class="churches">
      <LogoItem churche="Valencia"/>
      <LogoItem churche="Quibor"/>
    </div>
  </section>
  
  <!-- Banner info  -->
  <section class="banner wrapper" id="banner-info">
    <BannerInfo />
  </section>

</template>

<style lang="css" scoped>

  /* welcome */
  .welcome{
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 1rem;
  }
  .border-iframe{
    border-radius: 1.5rem;
    background-color: white;
    padding: 1rem;
    box-shadow: 10px 5px 15px #1a718481;
  }
  .border-iframe-2{
    border-radius: 1.5rem;
    background: linear-gradient(to top left, #74e2ec,#1a7084 ) ;
    padding: .5rem;
  } 
  .video{
    width: 100%;
    border-radius: 1rem;
  }
  .text-welcome{
    display: flex;
    align-items: center;
  }

  /* churches */
  .churches-content{
    display: flex;
    justify-content: center;
  }
  .churches{
    display: flex;
    justify-content: space-around;
    gap: 2rem;
    flex-wrap: wrap;
  }
  /* media queries */
  @media (max-width: 800px){
    .welcome{
      grid-template-columns: 1fr;
      place-items: center;
    }
    .content-text{
      text-align: center;
    }
    .banner{
      place-items: center;
    }
  }
  
</style>


