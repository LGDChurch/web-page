<template lang="">
    <div class="logo">
        <img src="../assets/lgd.png" width="40" alt="">
        <span class="lgd-l">LGD {{churche}}</span>
    </div>
</template>
<script setup>

defineProps({
    churche: {
        default: "",
        type: String
    }
})
</script>
<style lang="css">
    .logo{
        display: flex;
        align-items: center;
        gap: .5rem;
    }
    .lgd-l{
        font-weight: 600;
    }
</style>