<template>
  <div class="container" v-show="show">
        <div class="popup">
            <h1 class="title">Reporte por fecha de nacimiento</h1>
            <span class="sub-title">Ingresa los siguientes datos para generar tu reporte</span>
            <div class="form">
                <div class="form-group">
                    <span class="label">Descripción del reporte</span>
                    <input class="form-control" type="text">
                </div>
                <div class="form-group-date">
                    <span class="title">Fecha de nacimiento</span>
                    <div class="form-date">
                        <div class="form-date-initial">
                            <span class="label">Inicio</span>
                            <input class="form-control" type="date">
                        </div>
                        <div class="form-date-fin">
                            <span class="label">Fin</span>
                            <input  class="form-control" type="date">
                        </div>
                    </div>
                </div>
            </div>
            <div class="button" @click="generarReporte()">Generar reporte</div>
        </div>
  </div>
</template>

<script>
export default {
    props:{
        show: {}
    },

    methods: {
        generarReporte(){
            this.$router.go()
        }
    }

}
</script>

<style lang="scss" scoped>
.container{
    width: 100%;
    height: 100vh;
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgba(0,0,0,0.6);
    .popup{
        width: 100%;
        height: 417px;
        background: #FFFFFF;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        border-radius: 10px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        margin: 0 10px;
        padding: 10px;
        .title{
            font-family: 'Argentum Sans Bold';
            font-size: 24px;
            text-align: center;
            color: #181818;
            margin: 18px 0;
        }
        .sub-title{
            color: #565656;
            font-size: 14px;
            text-align: center;
            margin: 10px 0 38px 0;
        }
        .form{
           display: flex;
           justify-content: center;
           align-items: center;
           flex-direction: column;
           width: 100%;
           .form-group{
               display: flex;
               justify-content: center;
               align-items: center;
               flex-direction: column;
               position: relative;
               width: 100%;
               .label{
                   color: #696969;
                   font-size: 12px;
                   background-color: #fff;
                   padding: 0 5px;
                   position: absolute;
                   top: -5px;
                   left: 5px;
               }
               .form-control{
                    width: 100%;
                    height: 54px;
                    border: 1px solid rgba(0, 0, 0, 0.12);
                    box-sizing: border-box;
                    border-radius: 6px;
                    padding: 0 10px;
               }
           }
           .form-group-date{
               display: flex;
               justify-content: center;
               align-items: center;
               flex-direction: column;
               position: relative;
               width: 100%;
               .title{
                   width: 100%;
                   font-size: 12px;
                   margin: 15px 0;
                   color: #696969;
                   display: flex;
                   justify-content: flex-start;
                   font-family: 'Argentum Sans Light';
               }
               .form-date{
                   display: flex;
                   justify-content: center;
                   align-items: center;
                   flex-direction: row;
                   width: 100%;
                   .form-date-initial{
                        width: 50%;
                        position: relative;
                        margin: 0 5px 0 0;
                        .label{
                            position: absolute;
                            background-color: #fff;
                            font-size: 12px;
                            top: -5px;
                            left: 10px;
                            padding: 0 5px;
                        }
                        .form-control{
                            width: 100%;
                            height: 54px;
                            border: 1px solid rgba(0, 0, 0, 0.12);
                            box-sizing: border-box;
                            border-radius: 6px;
                            padding: 0 5px;
                        }
                    }
                    .form-date-fin{
                        width: 50%;
                        position: relative;
                        .label{
                            position: absolute;
                            background-color: #fff;
                            font-size: 12px;
                            top: -5px;
                            left: 10px;
                            padding: 0 5px;
                        }
                        .form-control{
                            width: 100%;
                            height: 54px;
                            border: 1px solid rgba(0, 0, 0, 0.12);
                            box-sizing: border-box;
                            border-radius: 6px;
                            padding: 0 5px;
                        }
                    }
                }
            }
        }
        .button{
            width: 180px;
            height: 45px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 16px;
            color: #181818;
            background: #CFCFCF;
            box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
            border-radius: 50px;
            margin: 20px 0px;
            cursor: pointer;
        }
    }
}

@media (min-width: 768px){
    .container{
        .popup{
            width: 526px;
            .button{
                width: 227px;
                height: 51px;
            }
        }
    }
}
</style>