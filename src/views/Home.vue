<template>
  <div class="container">
    <toolbar/>
    <div class="reportes">
      <h1 class="title">Generador de reportes TK</h1>
      <div class="historial-reportes"> 
      
      </div>
      <div class="button" @click="crearReporte()">Crear reporte</div>
    </div>
    <popup v-show="show"/>
  </div>
</template>

<script>
import toolbar from '../components/toolbar.vue'
import popup from '../components/popup.vue'
export default {
  data(){
    return{ 
      show: false
    }
  },

  components:{
    toolbar,
    popup
  },

  methods:{
    crearReporte(){
      this.show = true
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  .reportes{
    width: 690px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin: 0 8px;
    .title{
      text-align: center;
      font-size: 23px;
      font-weight: 400;
      line-height: 33px;
      color: #181818;
      margin: 0 0 98px 0;
    }
    .historial-reportes{
      width: 100%;
      height: 212px;
      margin: 0 0 30px 0;
      background: #4563E6;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .button{
      width: 187px;
      height: 43px;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #FFBE12;
      box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
      border-radius: 50px;
      cursor: pointer;
    }
  }
}

@media (min-width: 768px) {
  .container {
    .reportes{
      .title{
        font-size: 28px;
      }
      .historial-reportes{
        width: 100%;
        height: 212px;
        margin: 0 0 30px 0;
        background: #4563E6;
        border-radius: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
      }
      .button{
        width: 187px;
        height: 43px;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #FFBE12;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        border-radius: 50px;
        cursor: pointer;
      }
    }
  }
}
</style>
