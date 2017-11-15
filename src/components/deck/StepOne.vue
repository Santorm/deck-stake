<template>
  <section class="section">
        <h1>Escribe el título de tu problemática</h1>
        <input v-model="inputTitle" id="inputquestion" type='text' placeholder='Ejemplo: Control de mascotas en Madrid'>

        <p>Piensa en un tema cívico en el mundo real</p>
        <p>Considera un problema que afecte y sea relevante para tu comunidad</p>
        <p>Toma en cuenta en qué contexto ocurre el problema</p>
        <p><b>Requisito: El título debe ser corto de alrededor de tres palabras</b></p>

        <button v-on:click="clickeado">Hola</button>
{{$data}}
</section>
</template>

<script>
// import {validationMixin} from 'vuelidate'
// import {required, email} from 'vuelidate/lib/validators'

export default {
  name: "stepone",
  props: ["clickedNext", "currentStep"],
  //   mixins: [validationMixin],
  data() {
    return {
      inputTitle: ""
    };
  },
  // updated: function() {
  //   if (this.inputTitle != "") {
      
  //     this.$emit("can-continue", { value: true });
  //   } else {
  //     this.$emit("can-continue", { value: false });
  //   }
  // },
  methods: {
    clickeado: function(event) {
      // console.log("Button is clicked")
      //               if(true) {
      //                   this.$emit('can-continue', {value: true});
      //               } else {
      //                   this.$emit('can-continue', {value: false});
      //               }
      //           }
    }
  },
  created: {
     function(){

     this.$emit("can-continue", { value: true });
     }
  },
  watch: {
    inputTitle: function(val) {
      
      if (this.inputTitle != "") {

        console.log("Dentro de watch")
        this.$emit("can-continue", { value: true });
      } else {
        this.$emit("can-continue", { value: false });
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#inputquestion {
  width: 600px;
  height: 40px;
  font-size: 16px;
  border-radius: 5px;
  padding: 5px;
  background-color: aliceblue;
  text-align: center;
  margin-bottom: 50px;
}
</style>
