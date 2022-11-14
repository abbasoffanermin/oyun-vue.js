<template>
  <div>
    <button id="yenioyun" @click="yenioyun">oyuna basla</button>
   <div id="dv" class="d-none">
    <h2>Canavar:{{count1}} </h2>
    <button @click="hucum">Hucum</button>
    <button id="shucum" @click="shucum">Şiddətli hucum</button>
    <button id="xal" @click="xal">Xal toplamaq</button>
    <button @click="bitir">bitir</button>
    <h1>{{counter1}}</h1>
    <h3>{{counter2}}</h3>
   </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data(){
    return{
    count1:100,
    counter1:0,
    counter2:0
  
  }
  },
  methods:{
    yenioyun(){
      document.querySelector("#yenioyun").classList.add("d-none")
      document.querySelector("#dv").classList.remove("d-none")
    },
  hucum(){
    if(this.count1>0){
      this.count1-=Math.round(Math.random()*10)
      
    }else{
     this.count1=0
    }

  
  },
  shucum(){
    if(this.count1>0 &&  !document.querySelector("#shucum").className){
      this.count1-=Math.round(Math.random()*35)
      this.counter1+=1
    }else if(this.count1>0){
     this.count1=0
    }
  },
  xal(){
    if(this.count1<100 &&  !document.querySelector("#shucum").className){
      this.count1+=Math.round(Math.random()*20)
      this.counter2+=1
    }else{
     this.count1=100
    }
  },
 bitir(){
  location.reload()

}
  },
  watch : {
              counter1:function() {
                if(this.counter1==2){
                  document.querySelector("#shucum").setAttribute("class","btn disabled")
                }
                  
                 
               },
               counter2:function() {
                if(this.counter2==2){
                  document.querySelector("#xal").setAttribute("class","btn disabled")
                }
                  
                 
               },
}
  
}
</script>

