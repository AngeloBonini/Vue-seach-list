.<template>
  <div class="conversor">
    <h2>{{ baseCoin }} para {{ convertedCoin }}</h2>
    <input type="text"  v-model="baseCoin_value" v-bind:placeholder="baseCoin">
    <input type="button" value="Converter">
    <h2>{{convertedCoin_value}}</h2>
  </div>
</template>

<script>
export default {
name: "Conversor",
props: ["baseCoin", "convertedCoin"],

data(){
  return {
    baseCoin_value : "",
    convertedCoin_value : 0,
  }
},
methods: {
  converter(){
    
  }
}
};
</script>

<style scoped>
</style>
