<template>
    <div>
<Conversor base-coin="USD" convertedCoin="BRL"/>
<p></p>
    <search-input @gifs-fetched="onGifsFetched"/>

    <gif-list :gifs="gifs"/>
    
    </div>
</template>

<script>
import SearchInput from "@/components/SearchInput";
import GifList from "@/components/GifList";
import Conversor from "@/components/Conversor";
export default {
  name: 'App',
  components: {
    GifList,
    SearchInput,
    Conversor
  },
  data() {
    return {
      gifs: [],
    }
  },
  methods: {
    onGifsFetched(result) {
      console.log(result);
      this.gifs = result.data
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  padding: 50px
}
#app {
  width: 800px;
  margin: 0 auto;
}
</style>