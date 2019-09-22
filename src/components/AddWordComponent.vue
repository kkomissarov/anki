<template>
  <section class="container-fluid modal-wrapper">
    <div class="row vh-100">
      <div class="col-xl-4 m-auto p-4 bg-light border">
          <h2 class="mb-3">Add new word</h2>
          <form class="add-new-word" id="AddWordForm" @submit.prevent="onAddWordSubmit">
            <div class="form-group">
              <label>Word</label>
              <input
                type="text"
                class="form-control"
                name="word"
                v-model="word"
                autocomplete="off"
                required>
            </div>

            <div class="form-group">
              <label>Translate</label>
              <input
                type="text"
                class="form-control"
                name="translate"
                v-model="translate"
                autocomplete="off"
                required>
            </div>

            <div class="form-group">
              <label>Context</label>
              <textarea
                class="form-control"
                rows="4"
                name="context"
                v-model="context">
              </textarea>
            </div>

            <button class="btn btn-secondary">Add</button>
            <button
              type="button"
              class="btn btn-secondary"
              @click="$emit('change-state', 'default')">
              Close
            </button>
          </form>
      </div>
    </div>
  </section>
</template>



<script>
export default {
  data(){
    return{
      word: null,
      translate: null,
      context: null
    }
  },
  methods: {
    onAddWordSubmit(){
      this.$emit('change-state', 'loading');

      this.axios.post('http://127.0.0.1:8000/api/v1.0/word/create/', {
        'word': this.word,
        'translate': this.translate,
        'context': this.context
      })
      .then(()=>{
        this.$emit('change-state', 'default');
      });

    }
  }
};
</script>

<style>
.add-new-word .btn{
  margin: 0px 7px;
}
.add-new-word button:first-of-type{
  margin-left: 0px;
}
.add-new-word button:last-of-type{
  margin-right: 0px;
}
</style>
