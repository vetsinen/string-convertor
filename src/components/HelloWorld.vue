<template>
  <div class="hello">
    <input v-model="str">
    <h1>{{ str }}</h1>
    <h1>{{ reversedMessage }}</h1>
  </div>
</template>

<script>
function camelCase(...keys) {
  return keys
      .map((k) => (/[a-z]/.test(k) ? k : k.toLowerCase()))
      .map((k) => k.split(/[^A-Za-z0-9]+/))
      .flat()
      .map((k, i) =>
          i
              ? k.charAt(0).toUpperCase() + k.slice(1)
              : k.charAt(0).toLowerCase() + k.slice(1)
      )
      .join('');
}

export default {
  name: 'HelloWorld',
  data(){
    return {
      str: 'abc fff ddd',
      proced: this.str
    }
  },
  computed: {
    reversedMessage: function () {
      // `this` указывает на экземпляр vm
      return camelCase('httpError', this.str)
      //return this.str.split('').reverse().join('')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
