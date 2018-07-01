<template>
  <div class="hello" @touchstart = 'onStart' 
                 @touchend = 'onEnd' id='hello'>
        <!-- <div class='content'> -->
            <div class='main-content' id='main-content'>
                   <div v-for='(item,index) in list'    :key='index' class='list'>
                  <h2>{{item.name}}</h2>
                  <h4>{{item.life}}</h4>
             </div>
            </div>
        <!-- </div> -->
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {  
      msg: 'Welcome to Your Vue.js App'
    }
  },
  data(){
    return {
         list:[
             {
               name:'乔布斯',
               life:'一生追随激情'
             },
              {
               name:'伊隆·马斯克',
               life:'在火星上退休'
             },
              {
               name:'贝索斯',
               life:'万货商店'
             },
              {
               name:'杰克韦尔奇',
               life:'一生奉献一家企业'
             },
              {
               name:'王石',
               life:'一生为理想，不断提升人生高度'
             },
             {
               name:'海伦凯勒',
               life:'不幸的，也是最幸运的，一生向光明'
             },
              {
               name:'富兰克林',
               life:'不断自我培养与训练，探索人性所能达到的境界'
             },
              {
               name:'蓝血十杰',
               life:'带人类进入现代管理学'
             },

         ]
    }
  },
  methods:{
       onStart(e){
           console.log('缘起',e.changedTouches[0].clientY)
       },
       onEnd(e){
console.log('缘灭',e.changedTouches[0].clientY)
     const h1 = document.getElementById('main-content').offsetHeight;
     const h2 = document.getElementById('hello').scrollTop;
     const h3 = 400;
     if(h1-h2==h3){
       console.log('引爆核弹')
     }
     console.log('最遥远的距离',h1,h2)
     
       }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  *{
    padding:0;
    margin:0;
  }
  .hello{
    width:100%;
    height:400px;
    background:#eee;
    overflow:scroll;

  }
  .content{
      width:80%;
      /* height:1000px; */
      margin:0 auto;
      background:#aa459c;
  }
  .list:nth-of-type(2n+1){
     background:yellow;
  }
   .list:nth-of-type(2n){
     background:#fff;
  }

</style>
