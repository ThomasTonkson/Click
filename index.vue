<template>
  <div>
  <img>
    Niggas lost :  {{$store.state.counter}}
    <img @click="addCookies"
         src="https://www.pngkey.com/png/full/19-192944_thanos-head-png-thanos-png.png"></img>
    <button :disabled="$store.state.counter<10" @click="addPerSecond" class="btn btn-primary">auto click</button>
    <button :disabled="$store.state.counter<15" @click="addBy" class="btn btn-primary">Upgrade</button>
  </div>
</template>

<script>
  export default {
      mounted(){
          setInterval(()=>{
              this.$store.dispatch('increment', this.$store.state.perSecond);
          }, 100);
      },
      methods:{
          addCookies(){
              this.$store.dispatch('increment', this.$store.state.By);
          },
          addPerSecond(){
              this.$store.dispatch('incrementPerSecond', 1);
              this.$store.dispatch('increment', -10);
          },
          addBy(){
              this.$store.dispatch('increment', -15);
              this.$store.dispatch('incrementBy');
          }
      }
  }
</script>

<style scoped>
  img{
    height: 300px;
    width: 300px;
  }

</style>
