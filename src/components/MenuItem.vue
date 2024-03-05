<script setup>
import { onMounted, ref } from 'vue';
import LogoItem from './LogoItem.vue' 

const currentPositionMenu = ref('')
onMounted( ()=> {
    
    document.addEventListener('scroll', () =>{
        let scrollTop = document.documentElement.scrollTop;

        currentPositionMenu.value = scrollTop !== 0;
    })
})

</script>

<template>
    <div class="headband">
        <div class="content-social-headband">
            <a href="https://www.facebook.com/profile.php?id=100064372282296&locale=es_LA" target="_blank">
                <i class="bi bi-facebook"></i>
                Iglesia La Gracia De Dios
            </a>
        </div>
        <div class="content-social-headband">
            <a href="https://www.instagram.com/lgdtelevision/" target="_blank">
                <i class="bi bi-instagram"></i>
                lagraciad
            </a>
        </div>
        <div class="content-social-headband">
            <a href="https://www.youtube.com/@lgdtelevision8153" target="_blank">
                <i class="bi bi-youtube"></i>
                @lgdtelevision8153
            </a>
        </div>
        <div class="content-social-headband">
            <a href="https://www.tiktok.com/@lagraciadedios23" target="_blank">
                <i class="bi bi-tiktok"></i>
                @lagraciadedios23
            </a>
        </div>
    </div>
    <header :class="{  'bg' : currentPositionMenu }" id="header" >
        <nav class="nav">
            <LogoItem />
            <ul class="nav-ul">
                <li class="nav-li">
                    <a href="#welcome">Inicio</a>
                </li>
                <li class="nav-li">
                    <div class="point"></div>
                    <a href="">Sala en vivo</a>
                </li>
            </ul>       
        </nav>
    </header>
</template>

<style lang="css" scoped>
    .bi-facebook, .bi-instagram, .bi-youtube, .bi-tiktok{
        font-size: .5rem;
    }
    .content-social-headband{
        display: flex;
        gap: .5rem;
        align-items: center;
    }
    .content-social-headband a{
        color: white;
    }
    header{
        position: sticky;
        top: 0;
        z-index: 2;
    }
    .bg{
        background-color: #eefcfd63;
        backdrop-filter: blur(10px);
        box-shadow: 0 2px 12px rgba(147, 177, 183, 0.461) ;
    }
    .nav{
        display: flex;
        padding:  .75rem ;
        width: 100%;
        max-width: 1580px;
        margin: auto;
    }
    .lgd-l{
        font-size: 1.2rem;
        font-weight: 700;
    }
    .logo{
        display: flex;
        align-items: center;
    }
    .nav-ul{
        display: flex;
        justify-content: end;
        align-items: center;
        padding: 0 1.75rem;
        gap: 1.75rem;
    }
    .nav-li{
        list-style: none;
        display: flex;
        align-items: center;
        gap: .5rem;
    }
    .nav-li a {
        text-decoration: none;
        white-space: nowrap;
    }
    .point{
        width: 7px;
        height: 7px;
        border-radius: 50%;
        background: rgb(234, 82, 82);
        animation-name: tip;
        animation-duration: 2s;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
    }
    @keyframes tip{
        0%{
            background-color: rgb(234, 82, 82);
        }
        50%{
            background-color: rgba(244, 31, 31, 0.109);
        }
        100%{
            background-color: rgb(234, 82, 82);
        }
    }
</style>