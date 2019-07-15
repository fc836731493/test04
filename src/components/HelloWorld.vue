<template>
  <div class="hello">
    <div>
      <ul>
        <li v-for="news in newsData" >
           <p>{{ news.screen_name }}</p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
     newsData:[]
    }
  },
  created(){
      this.$axios("https://www.apiopen.top/satinApi")
      .then(res => {
         this.newsData = res.data;
         console.log(res.data);
      })
      .catch(error => {
        console.log(error);
      })
  }
}
</script>

<style >

</style>
