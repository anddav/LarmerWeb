<template>
  <div class="larmer-main" :class="modifiers">
    <h1 class="header">Larmer Web</h1>
    <div class="row ">
      <div class="col-lg row-content"><Button class="btn btn-lg btn-danger" @click="() => onClick('red')">Red</Button></div>
      <div class="col-lg row-content"><Button class="btn btn-lg btn-success" @click="() => onClick('green')">Green</button></div>
      <div class="col-lg row-content"><Button class="btn btn-lg btn-primary" @click="() => onClick('blue')">Blue</button></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "LarmerMain",
  data() {
    return {
      currentColor: 'green'
    } 
  },
  props: { 
    msg: String 
  },
  computed: {
    modifiers () {
      return {
        'larmer-bg-red': this.currentColor === 'red',
        'larmer-bg-green': this.currentColor === 'green',
        'larmer-bg-blue': this.currentColor === 'blue'
      }
    }
  },
  methods: {
    onClick(color){
      this.currentColor = color;
    }
  }
}
</script>
<style>
.larmer-main {
  /* background: green; */
  padding: 2rem;
  min-height: 100vh;
  text-align: center;
}
.larmer-bg-red {
  background: red;
}
.larmer-bg-green {
  background: green;
}
.larmer-bg-blue {
  background: blue
}
.header {
  color: darkslategray;
}
.row-content {
  padding-top: 1rem;
}
</style>