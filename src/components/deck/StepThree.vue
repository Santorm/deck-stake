<template>
  <section class="section">
        <h1>ESCRIBE EL TÍTUTLO DE LA PROBLEMÁTICA</h1>
        <input type='text' placeholder='Cómo poner aqui la pregunta ejemplo'>

        <p>Tip: Piensa en un tema cívico en el mundo real</p>
        <p>Tip: Piensa en un tema cívico en el mundo real</p>
        <p>Tip: Piensa en un tema cívico en el mundo real</p>
        <p><b>Requisito: El título debe ser corto de alrededor de tres palabras</b></p>

</section>
</template>

<script>

// import {validationMixin} from 'vuelidate'
// import {required, email} from 'vuelidate/lib/validators'


export default {
  name: 'stepone',
  props: ['clickedNext', 'currentStep'],
//   mixins: [validationMixin],
        data() {
            return {
                
            }
        }
        
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
