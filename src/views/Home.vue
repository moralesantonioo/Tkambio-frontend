<template>
  <div class="container">
    <toolbar/>
    <div class="reportes">
      <h1 class="title">Generador de reportes TK</h1>
      <div class="historial-reportes"> 
        <div class="historial-reportes-header"> 
          <div class="data-header">
            <div class="data-content" >
              <span>Titulo</span>
              <span>Fecha de creacion</span>
              <span>Acción</span>
            </div>
            <div class="linea"></div>
          </div>
        </div>
        <div class="section-reports">  
          <div class="reports">
            <div class="data" v-for="data in datos" :key="data">
              <div class="data-content">
                <span>{{data.title}}</span>
                <div class="lineaR"></div>
                <span>{{data.date}}</span>
                <div class="lineaR"></div>
                <span>{{data.action}}</span>
              </div>
              <div class="linea2"></div>
            </div>
          </div>
        </div>
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
      show: false,
      datos: [
        {
          title: 'Reporte de usuario 1',
          date: '04/02/2020',
          action: 'Descargar'
        },
        {
          title: 'Reporte de usuario 2',
          date: '08/05/2021',
          action: 'Descargar'
        },
        {
          title: 'Reporte de usuario 3',
          date: '20/08/2021',
          action: 'Descargar'
        }
      ]
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
      .historial-reportes-header{
        width: 100%;
        .data-header{
          width: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          .data-content{
            width: 100%;
            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-direction: row;
            color: #fff;
            font-size: 14px;
            padding: 10px 0 0 0;
          }
          .linea{
            width: 95%;
            height: 4px;
            background: #C4C4C4;
             margin: 10px 0px;
          }
        } 
      }
      .section-reports{
        width: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        //margin: -80px 0 10px 0;
        .reports{
          width: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          .data{
            width: 100%;
            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-direction: column;
            font-size: 12px;
            .data-content{
              width: 100%;
              display: flex;
              justify-content: space-around;
              align-items: center;
              flex-direction: row;
              padding: 8px 0;
              .lineaR{
                width: 4px;
                height: 20px;
                background: #C4C4C4;
              }
            }
            .linea2{
              width: 95%;
              height: 1px;
              background: #C4C4C4;
            }
          }
        }
      }
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
