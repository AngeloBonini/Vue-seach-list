.<template>
  <div class="conversor">
    <h2>{{ baseCoin }} para {{ convertedCoin }}</h2>
    <input type="text"  v-model="baseCoin_value" v-bind:placeholder="baseCoin">
    <input type="button" value="Converter" v-on:click="converter">
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
    
    let de_para = this.baseCoin + "_" + this.convertedCoin;

    let url = "https://free.currconv.com/api/v7/convert?q="+
    de_para
    +"&compact=ultra&apiKey=2a1f4df820cf5ab592ea";

    fetch(url).then(res=> {
      return res.json();
    }).then(json =>{
      console.log(json);
      let cotacao =json[de_para];
      this.convertedCoin_value = (cotacao * parseFloat(this.baseCoin_value)).toFixed(2);
    })
  }
}
};
</script>

<style scoped>

.conversor{

  max-width: 300px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  padding: 20px;
}
</style>
