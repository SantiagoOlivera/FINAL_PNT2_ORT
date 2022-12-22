<template lang="html">

  <section class="src-components-finalpnt-2">
    <h1>Conversor de temperatura</h1>
    <label>Temperatura en C°</label>
    <br />
    <input type="number" v-model.number="temperatura" />
    <br />
    <p :class="style()">Temperatura en F°: {{ this.tempF }}</p>
    <br />
    <p :class="style()">Temperatura en K°: {{ this.tempK }}</p>

    <h1>Respuestas preguntas</h1>
    <p>1) C </p>
    <p>2) B </p>
    <p>3) C </p>
    <p>4) A </p>
    <p>5) B </p>
    
    
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-finalpnt-2',
    props: [],
    mounted () {

    },
    data () {
      return {
        temperatura: 0,
        DECIMALES: 2,
      }
    },
    methods: {
      style(){
        var style = 'rojo';
        if(this.temperatura <= 0){
          style = 'azul';
        }else if(this.temperatura > 0 && this.temperatura < 15){
          style = 'magenta';
        }
        return style;
      }
    },
    computed: {
      tempF(){

        var ret = null;

        if(!isNaN(this.temperatura) && this.temperatura !== ''){
          ret = ( (this.temperatura * 1.8) + 32 ).toFixed(this.DECIMALES)
        }

        //console.log(isNaN(this.temperatura));

        return ret;

      },
      tempK(){

        var ret = null; 

        if(!isNaN(this.temperatura) && this.temperatura !== ''){
          ret = ( this.temperatura + 273.15 ).toFixed(this.DECIMALES);
        }

        //console.log(isNaN(this.temperatura));

        return ret;

      }
    }
}


</script>

<style scoped lang="css">
  .src-components-finalpnt-2 {

  }
  .azul{
    color: blue;
  }
  .magenta{
    color:magenta;
  }
  .rojo{
    color:red;
  }

</style>
