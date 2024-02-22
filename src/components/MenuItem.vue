<script setup>
import { onMounted, ref } from 'vue';
import LogoItem from './LogoItem.vue' 

const currentPositionMenu = ref('')
onMounted( ()=> {
    
    document.addEventListener('scroll', (event) =>{
        let scrollTop = document.documentElement.scrollTop;

        (scrollTop === 0 ) ?  currentPositionMenu.value = false :  currentPositionMenu.value = true   
    })
})

</script>

<template>
    <div class="headband">
        <div class="content-social-headband">
            <i class="bi bi-facebook"></i>
            Iglesia La Gracia De Dios 
        </div>
        <div class="content-social-headband">
            <i class="bi bi-instagram"></i>
            lgdtelevision
        </div>
        <div class="content-social-headband">
            <i class="bi bi-youtube"></i>
            LGD TELEVISION
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
    .bi-facebook, .bi-instagram, .bi-youtube{   
        font-size: .5rem;
    }
    .content-social-headband{
        display: flex;
        gap: .5rem;
        align-items: center;
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