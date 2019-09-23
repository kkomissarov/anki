<template>

  <div
    id="app"
    @change-state='changeState($event)'>

      <div class="container-fluid">
        <div class="row vh-100">
          <component
            v-bind:is="currentComponent"
            v-on:change-state="changeState($event)">
          </component>
        </div>
      </div>
  </div>

</template>

<script>
import WordArea from './components/WordArea.vue';
import AddWordComponent from './components/AddWordComponent.vue';
import LoadingSpinner from './components/LoadingSpinner.vue';

export default {
  name: 'app',
  components: {
    'wordarea': WordArea,
    'adding': AddWordComponent,
    'loading': LoadingSpinner
  },
  data() {
    return{
      currentState: 'wordarea'
    }
  },
  methods: {
    changeState(state){
      this.currentState = state;
    }
  },
  computed: {
    currentComponent(){
      return this.currentState
    }
  }
}
</script>
