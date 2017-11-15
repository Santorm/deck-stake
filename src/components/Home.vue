<template>
  <section class="section">
    <div class="container">
        <div class="columns">
            <div class="column is-8 is-offset-2">
                <horizontal-stepper :steps="demoSteps" @completed-step="completeStep"
                                    @active-step="isStepActive" @stepper-finished="alert"
                >                     
                </horizontal-stepper>
            </div>
        </div>
    </div>
</section>
</template>

<script>
import HorizontalStepper from 'vue-stepper';

    // This components will have the content for each stepper step.
import StepOne from './deck/StepOne.vue';
import Steptwo from './deck/Steptwo.vue';

export default {
  name: 'home',
  components: {
            HorizontalStepper
        },
  data () {
    return {
                demoSteps: [
                    {
                        icon: 'mail',
                        name: 'first',
                        title: 'Primer Paso',
                        subtitle: 'Subtitle sample',
                        component: StepOne,
                        completed: false

                    },
                    {
                        icon: 'report_problem',
                        name: 'second',
                        title: 'Sample title 2',
                        subtitle: 'Subtitle sample',
                        component: Steptwo,
                        completed: false
                    }
                ]
            }
  },
  methods: {
            // Executed when @completed-step event is triggered
            completeStep(payload) {
                this.demoSteps.forEach((step) => {
                    if (step.name === payload.name) {
                        step.completed = true;
                    }
                })
            },
            // Executed when @active-step event is triggered
            isStepActive(payload) {
                this.demoSteps.forEach((step) => {
                    if (step.name === payload.name) {
                        if(step.completed === true) {
                            step.completed = false;
                        }
                    }
                })
            },
            // Executed when @stepper-finished event is triggered
            alert(payload) {
                alert('end')
            }
        }
     
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
