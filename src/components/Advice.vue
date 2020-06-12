<template>
    <div>
        <p> {{ info }} </p>
        <button @click="getAdvice" class="btn btn-primary">Get Advice</button>
    </div>
</template>

<script>
const axios = require('axios')

export default {
  name: 'Advice',
  data () {
    return {
      info: 'placeholder'
    }
  },
  methods: {
    getAdvice: function () {
      axios
        .get('https://api.adviceslip.com/advice')
        .then(response => (this.info = response))
    }
  }
}
</script>
