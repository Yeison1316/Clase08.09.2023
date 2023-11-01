<script setup>
  import {ref} from 'vue';
  let notifications = ref(0);
  function addValue() {
    notifications.value++;
  }
  function resValue(){
    if(notifications.value > 0){
      notifications.value--;
    }
  }


</script>
<template>
  <div class="wraper">
    <div class="foto">
        <div class="noti" v-if="notifications > 0">{{notifications}}</div>
    </div>
    <div class="boton_wraper">
      <div class="buton" @click="resValue">-</div>
      <div class="buton" @click="addValue">+</div>
    </div>
    <div v-if="notifications==0">
      Buu! nadie te escribre
    </div>
    <div v-if="notifications==0">
      Revisa tu inbox😎
    </div>
  </div>
</template>

<style scoped>

  .wraper{
    background-color:#9b726f;
    width:40%;
    margin:auto;
    border-radius:8px;
  }
  .foto{
    background-color:#f0e999;
    width:128px;
    height:128px;
    border-radius:100%;
    margin:auto;
    position:relative;
    background-image:url(https://img.freepik.com/fotos-premium/rana-gran-ojo-anteojos-que-dice-palabra-rana_890191-734.jpg);
    background-size:cover;
  }
  .noti{
    position:absolute;
    background-color:#eeb15b;
    width:auto;
    height:auto;
    padding:4px;
    border-radius:50%;
    display:flex;
    align-items:center;
    justify-content:center;
    color:aliceblue;
    top:0;
    right:0;
    overflow:hidden;
  }
  .boton_wraper{
    background-color:#f0e999;
    text-align:center;
    padding: 4px;
  }
  .buton{
    background-color:#c46564;
    border-radius:4px;
    padding:4px 4px;
    font-weight:bold;
    color:aliceblue;
    display:inline-block;
    width:40px;
    cursor:pointer;
  }
  .buton.first-child{
    margin-right:8px;
  }
  .buton.last-child{
    margin-left:8px;
  }

</style>

