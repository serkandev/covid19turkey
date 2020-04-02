<template>
  <div id="app" class="text-center" >
    <div class="container mt-4 text-center">
       <img src="./assets/corona.svg"   @mouseover="wash($event)"  class="covid covid1  animated fadeIn"  alt="" v-show="virus>10">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid2 animated fadeIn" alt=""  v-show="virus>30" >
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid3 animated fadeIn" alt="" v-show="virus>20">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid4 animated fadeIn" alt="" v-show="virus>40">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid5 animated fadeIn" alt="" v-show="virus>50">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid6 animated fadeIn" alt="" v-show="virus>60">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid6 animated fadeIn" alt="" v-show="virus>80">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid7 animated fadeIn" alt="" v-show="virus>70">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid8 animated fadeIn" alt="" v-show="virus>100">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid9 animated fadeIn" alt="" v-show="virus>90">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid10 animated fadeIn" alt="" v-show="virus>100">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid11 animated fadeIn" alt="" v-show="virus>110">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid12 animated fadeIn" alt="" v-show="virus>130">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid13 animated fadeIn" alt="" v-show="virus>120">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid14 animated fadeIn" alt="" v-show="virus>130">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid15 animated fadeIn" alt="" v-show="virus>140">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid16 animated fadeIn" alt="" v-show="virus>150">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid17 animated fadeIn" alt="" v-show="virus>160">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid18 animated fadeIn" alt="" v-show="virus>180">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid19 animated fadeIn" alt="" v-show="virus>170">
       <img src="./assets/corona.svg"   @mouseover="wash($event)" class="covid covid20 animated fadeIn" alt="" v-show="virus>190">
       <img src="./assets/corona2.svg"  @mouseover="wash($event)" class="covid covid21 animated fadeIn" alt="" v-show="virus>200">
       
      

       
      
       
      <h2 class="border shadow-md p-3 text-white font-weight-bold header">TÜRKİYE GÜNLÜK KORONAVİRÜS TABLOSU</h2>
      <div class="row mt-4">
        
      <div class="col-md-4 col-sm-12 mx-auto">
        <div class="card shadow">
          <div class="card-body text-center">
            <h2 class="title">Toplam Vaka</h2>
            <p class="iCountUp mt-2">
              <ICountUp
              :delay="delay"
              :endVal="this.cases"
              :options="options"
              
            />  
           
            </p>
          </div>
        </div>
      </div>
      <div class="col-md-4 col-sm-12 mx-auto mt-3 mt-sm-0">
        <div class="card shadow">
          <div class="card-body text-center">
            <h2 class="title">Bugünkü Vaka</h2>
            <p class="iCountUp" style="absolute">
              <ICountUp
              :delay="delay"
              :endVal="this.todayCases"
              :options="options"
              
            />  
           
            </p>
            
          </div>
          
        </div>
      </div>
      <div class="col-md-4 col-sm-12 mx-auto mt-3 mt-sm-0 ">
        <div class="card shadow">
          <div class="card-body text-center">
           <h2 class="title">Bugünkü Ölüm</h2>
            <p class="iCountUp ">
              <ICountUp
              :delay="delay"
              :endVal="this.todayDeaths"
              :options="options"
            />
            
            </p>
          </div>
        </div>
      </div>
    </div>
    
    <div class="row mt-3">
      <div class="col-md-4 col-sm-12 mx-auto">
        <div class="card shadow">
          <div class="card-body text-center">
            <h2 class="title">Toplam Ölüm</h2>
            <p class="iCountUp mt-2">
              <ICountUp
              :delay="delay"
              :endVal="this.deaths"
              :options="options"
            />  
           
            </p>
          </div>
        </div>
      </div>
      <div class="col-md-4 col-sm-12 mx-auto mt-3 mt-sm-0">
        <div class="card shadow">
          <div class="card-body text-center">
            <h2 class="title">Kurtarılan Hasta</h2>
            <p class="iCountUp mt-2">
              <ICountUp
              :delay="delay"
              :endVal="this.recovered"
              :options="options"
              
            />  
            
            </p>
            
          </div>
        </div>
      </div>
      <div class="col-md-4 col-sm-12 mx-auto mt-3 mt-sm-0 ">
        <div class="card shadow">
          <div class="card-body text-center">
           <h2 class="title">Durumu Kritik</h2>
            <p class="iCountUp mt-2">
              <ICountUp
              :delay="delay"
              :endVal="this.critical"
              :options="options"
             
            />  
           
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      
      <div class="col-12 mt-4">
        <div class="card shadow p-3 ">
          <div class="row">
            <div class="col-md-8  mx-auto ">
               <div class="row mt-3">
                 <div class="col-md-4 mx-auto">
                   <h3 class="lead">Hastalık Belirtileri</h3>
                   <hr>
                   <p> Yüksek Ateş</p>
                   <p>Öksürük</p>
                   <p>Nefes Darlığı</p>
                 </div>
                 <div class="col-md-4 mx-auto">
                   <h3 class="lead">Korunma Yolları</h3>
                   <hr>
                   <p>Evden Çıkma</p>
                   <p>Ellerini Sık Sık Temizle</p>
                   <p>Sosyal Mesafeye Dikkat Et</p>
                 </div>
               </div>
            </div>
            <div class="col-md-4">
               <img id="medic" src="./assets/medic.svg" alt=""> 
            </div>
          </div>
        </div>
      </div>
    </div>
    </div>
   <p class="mt-4 lead">developed by serkandev</p>
   <a href="https://github.com/novelcovid/api" class="text-decoration-none lead">Covid Api</a>
  </div>
</template>

<script>
import ICountUp from 'vue-countup-v2';
import axios from 'axios'
export default {
    components:{
        ICountUp
    },
      data () {
    return {
        delay: 50,
        endVal: 120500,
        options: {
          useEasing: true,
          useGrouping: true,
          separator: ',',
          decimal: '.',
          prefix: '',
          suffix: '',
         
        },
          cases: 15679,
          todayCases: 0,
          deaths: 277,
          todayDeaths: 0,
          recovered: 333,
          active: 15069,
          critical: 979,
          casesPerOneMillion: 186,
          deathsPerOneMillion: 3,
          virus:0,
         	selectedCursor: './assets/washhand.png'
    }
  },
  created(){
  
    axios.get("https://corona.lmao.ninja/countries/Turkey")
    .then(res=>{
      console.log(res.data);
      this.cases = res.data.cases;
       this.todayCases = res.data.todayCases;
       this.deaths = res.data.deaths;
       this.todayDeaths = res.data.todayDeaths;
       this.recovered = res.data.recovered;
       this.critical = res.data.critical;
    })
    setInterval(() => {
      this.virus+=10;
    }, 1500);
  },
  methods:{
    wash(e){
         e.target.style.display = "none";
    }
  }
}
</script>

<style >
    
    
    *{
      font-family: 'Noto Sans', sans-serif;
      color:#3f3844;
      
      font-weight: 700;
    }
    body{
      background:#eeeeee;
     
    }
   
    .iCountUp {
    font-size: 2.5em;
    margin: 0;
    color: #b4595e;
    
  }
  .header{
    background:#900C3F
  }
  img#medic{
    width:100%;
    height: 200px;
  }
  hr{
    border-top: 1px solid red;
  }
  .covid{
      height: 150px;
      position: absolute;
      z-index: 1;
  }
   
  .covid1{ 
    bottom:-25px;
    left:-35px;
  }
   .covid2{
     bottom:125px;
    left:-35px;
  }
   .covid3{
    bottom:275px;
    left:-35px;
  }
   .covid4{
      bottom:425px;
     left:-35px;
  }
   .covid5{
    bottom:575px;
    left:-35px;
  }
  .covid6{
    bottom:690px;
    left:-35px;
  }
  
   .covid7{ 
    bottom:25px;
    left:65px;
  }
   .covid8{
     bottom:175px;
    left:65px;
  }
   .covid9{
    bottom:325px;
    left:65px;
  }
   .covid10{
      bottom:475px;
     left:65px;
  }
   .covid11{
    bottom:575px;
    left:65px;
  }
  .covid12{
    bottom:720px;
    left:65px;
  }
  .covid13{ 
    bottom:-25px;
    left:175px;
  }
   .covid14{
     bottom:125px;
    left:175px;
  }
   .covid15{
    bottom:275px;
    left:175px;
  }
   .covid16{
      bottom:425px;
     left:175px;
  }
   .covid17{
    bottom:575px;
    left:175px;
  }
  .covid18{
    bottom:690px;
    left:175px;
  }
  .covid19{
    top:10px;
    left:175px;
  }
  .covid20{
    top:10px;
    left:-35px;
  }
  .covid21{
    top:10px;
    left:75px;
  }
  
  
  
  
  
  
 
</style>