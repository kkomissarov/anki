<template>
  <main class="container-fluid bg-white">
    <div class="row vh-100">
      <div class="col-xl-4 m-auto p-4 bg-light border text-center">
        <section class="word-area">
          <p class="word">Apple</p>
        </section>
        <section class="answer-area">
          <div class="answer">
            <p class="translate">Яблоко</p>
            <p class="context">I have an apple</p>
          </div>
        </section>
        <section class="buttons-area">
          <div class="frontside-buttons d-none">
            <button type="button" class="btn btn-secondary">Flip</button>
          </div>

          <div class="flipside-buttons">
            <button type="button" class="btn btn-secondary">Easy</button>
            <button type="button" class="btn btn-secondary">Medium</button>
            <button type="button" class="btn btn-secondary">Repeat</button>
          </div>
        </section>
      </div>
    </div>
    <ControlsComponent v-on:change-state="$emit('change-state', $event)" />

  </main>
</template>


<script>
import ControlsComponent from '@/components/ControlsComponent.vue';

export default {
  data(){
    return{
      word: null,
      translate: null,
      context: null
    }
  },
  components: {
    ControlsComponent
  }
};
</script>

<style>
  .word {
    font-size: 30px;
  }
  .translate {
    font-size: 20px;
  }
  .context {
    font-size: 14px;
  }
  .answer-area {
    min-height: 100px;
  }
  .flipside-buttons .btn{
    margin: 0px 7px;
  }
  .flipside-buttons button:first-of-type{
    margin-left: 0px;
  }
  .flipside-buttons button:last-of-type{
    margin-right: 0px;
  }
</style>
