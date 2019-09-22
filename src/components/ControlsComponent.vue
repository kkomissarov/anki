<template>
    <header class="menu">
      <ul class="p-3">
        <li><a href="">Word list</a></li>
        <li>
          <button
              class="btn btn-link"
              v-on:click="$emit('change-state', 'adding')">
              Add word
          </button>
        </li>
      </ul>
    </header>
</template>

<script>
export default {};
</script>

<style>
.menu{
  width: 100%;
  text-align: center;
  position: absolute;
  right: 0px;
  bottom: 0px;
}
.menu ul{
  padding: 0;
  list-style-type: none;
}
.menu ul li {
  display: inline-block;
  margin-right: 20px;
}
.menu ul li:last-child{
  margin-right: 0px;
}
</style>
