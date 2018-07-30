<template>
  <div>
  	<input type="text" v-model="input">
  	<p :value="input"></p>
  	<button v-on:click.prevent="request()">Request</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      input: '123'
    }
  },
  methods: {
  	request() {
  		var data = {
  			input: this.input
  		}
  		this.$http.post('http://laravel-backend/api/request', data)
  		.then(res => {
  			console.log(res);
  		});
  	}
  }
}
</script>

<style>

</style>
