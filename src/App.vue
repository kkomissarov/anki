<template>

  <div
    id="app"
    @change-state='changeState($event)'>

      <div class="container-fluid">
        <div class="row vh-100">
          <component
            v-bind:is="currrentComponent"
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
    WordArea,
    AddWordComponent,
    LoadingSpinner
  },
  data() {
    return{
      currentStateChoises: {
        'default': WordArea,
        'adding': AddWordComponent,
        'loading': LoadingSpinner
      },
      currentState: 'default'
    }
  },
  methods: {
    changeState(state){
      this.currentState = state;
    }
  },
  computed: {
    currrentComponent: function(){
      return this.currentStateChoises[this.currentState]
    }
  }
}
</script>
