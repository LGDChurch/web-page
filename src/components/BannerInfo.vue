<template>
    <div class="banner-info">
        <div>
            <div class="menu">
                <ul class="ul-menu">
                    <li @click="funMenu('location')" :class="{ active : isActiveLgd }">Ubícanos</li>
                    <li @click="funMenu('contact')" :class="{  active : isActiveContact }">Contáctanos</li>
                    <li @click="funMenu('service')" :class="{  active : isActiveServiceDo } ">Servicios</li>
                </ul>
            </div>
            <div v-if="isActiveLgd" class="content-menu-selected">
                <div class=" section-map">
                    <div class="about-map" id="map">
                        <iframe class="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d62855.56701283605!2d-69.43395986588139!3d10.060279354288047!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8e876371e8a114f3%3A0x18d808a5764e5850!2sIGLESIA%20EVANGELICA%20LA%20GRACIA%20DE%20DIOS!5e0!3m2!1ses!2sve!4v1708652689889!5m2!1ses!2sve" scrolling="none" gesture-zoom="none" height="350" allowfullscreen loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
                    </div>
                </div>
            </div>
            <div v-else-if="isActiveContact" class="content-menu-selected">
                <div class="content-contact">
                    <div class="contact">
                        <i class="bi bi-google"></i>
                        <span>Correo : <br> iglesiaevanglagraciadedios@gmail.com</span>
                    </div>
                    <div class="contact">
                        <i class="bi bi-telephone-fill"></i>
                        <span>Telefono: <br>+58 424-5291151</span>
                    </div>
                </div>
            </div>
            <div v-else>
                <div class="content-contact">
                    <div class="contact">
                        
                        <span>Servicios Dominicales: <br> Domingos 9:00am a 12:00pm</span>
                    </div>
                    <div class="contact">
                        
                        <span>Servicios de oración: <br> Miércoles 7:00pm a 9:00pm</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    let isActiveLgd = ref(true)
    let isActiveContact = ref(false)
    let isActiveServiceDo = ref(false)

    const funMenu = (menuClick) => { 
        if(menuClick === 'location'){
            isActiveLgd.value = true
            isActiveContact.value = false
            isActiveServiceDo.value = false
        }
        if(menuClick === 'contact'){
            isActiveLgd.value = false
            isActiveContact.value = true
            isActiveServiceDo.value = false
        }
        if(menuClick === 'service'){
            isActiveLgd.value = false
            isActiveContact.value = false
            isActiveServiceDo.value = true
        }
    }
</script>

<style lang="css" scoped>
   
   .content-contact{
        display: grid;
        grid-template-columns: 1fr 1fr;
        margin-top: 1rem;
        grid-gap: 1rem;
   }
   @media (max-width: 800px){
    .content-contact{
        grid-template-columns: 1fr;
    }
   }
  
   .menu{
        display: flex;
        justify-content: center;
   }

   .contact{
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        justify-content: center;
        gap: 1rem;
        padding: 1rem;
        background-color: #1e5b6c;
        color: white;
        border-radius: 1rem;
        min-width: 100px;
        min-height: 200px;
        word-break: break-all;
   }
   .contact .bi{
        font-size: 2.5rem;
        color: white;
   }
   .ul-menu{
        display: flex;
        justify-content: center;
        align-items: center;
        list-style-type: none;
        gap: 2rem;
        position: relative;
   }
    @media (max-width: 768px) {
        .ul-menu{
            /* flex-direction: column; */
            font-size: 10px;
            gap: 0;
        } 
    }
   .ul-menu::after{
        content: '';
        position: absolute;
        bottom: 0;
        height: 4px;
        width: 100%;
        background: rgba(113, 112, 112, 0.455);
        border-radius: 1rem;
   }
   .ul-menu li{
        padding: .25rem;
        cursor: pointer;
   }
   .ul-menu li.active{
        padding: 10px;
        border-bottom: 4px solid var(--scooter-800);
   }
   .section-map{
    display: flex;
    justify-content: center;
  }
  .about-map{
    position: relative;
    padding: 1rem;
    margin-top: 1rem;
    border-radius: 1rem;
    box-shadow: 0 0px 10px rgba(72, 121, 147, 0.446) ;
    background: white;
    width: 100%;
    max-width: 600px;
  }
  .about-map::before{
    content: 'BARRIO BOLÍVAR CALLE 1 ENTRE CARRERAS 3 Y 4 3001 Barquisimeto, Estado Lara, Venezuela';
    position: absolute;
    color: white;
    left: -50px;
    top: 50%;
    transform: translatey(-50%);
    max-width: 250px;
    border-radius: 1rem;
    padding: .75rem;
    background-color: #1e5b6c;
    box-shadow: 0 0 5px rgba(46, 61, 94, 0.452);
    opacity: 0;
    transition: opacity .3s;
  }
  .about-map:hover::before{
    opacity: 1;
  }
  .map{
    border-radius: 1rem;
    width: 100%;
    border: none;
  }
</style>