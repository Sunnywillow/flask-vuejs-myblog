<template>
    <div>
      <p>{{ msg }}</p>
    </div>
</template>

<script>
    export default {
        name: "Ping.vue",
        data() {
          return {
            msg: 'Pong！'
          }
        },
      methods: {
          getMessage () {
            const path = 'http://localhost:5000/api /pong'
            axios.get(path)
              .then((res) => {
              this.msg = res.data;
            })
            .catch((error) => {
              //  eslint-disable-next-line
              console.error(error);
            })


          }
      },
      created() {
          this.getMessage()
      }
    }
</script>

<style scoped>

</style>
