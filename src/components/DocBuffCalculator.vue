<template>
    <div>
      <form class="form1" action="">
        <label class="subtitle"><h3>Buff Crafting Calculator</h3></label>
        <label for="asds">Component Power</label>
        <label for="asds">ASDS</label>
        <input id="asds" v-model.number="asds" type="number">

        <label for="acrm">ACMRDM</label>
        <input id="acrm" type="number" v-model.number="acrm">

        <label for="abec">ABEC</label>
        <input class="last" id="abec" type="number" v-model.number="abec">
        <label><img src="https://galaxyharvester.net/images/resources/meat.png" title="avian meat" alt="avian meat" /></label>
        
        <label for="avoq">OQ</label>
        <input id="avoq" type="number"  v-model.number="avoq">
        <label for="avpe">PE</label>
        <input id="avpe" type="number"  v-model.number="avpe">
        <label for="avdr">DR</label>
        <input class="last" id="avdr" type="number"  v-model.number="avdr">
        
        <label ><img src="https://galaxyharvester.net/images/resources/gas_reactive.png" /></label>
        <label for="rvoq">OQ</label>
        <input id="rvoq" type="number"  v-model.number="rvoq">
        <label for="rvpe">PE</label>
        <input id="rvpe" type="number"  v-model.number="rvpe">
        <label for="rvdr">DR</label>
        <input id="rvdr" class="last" type="number"  v-model.number="rvdr">
        </form>

        <p>Power: {{ totalPower }} </p>
        <p>Duration: {{ totalDuration }} </p>
        <p>
        
        </p>

     </div>   
</template>

<script>
export default {
  data() {
    return {
       "asds" : 0,
       "acrm" : 0,
       "abec" : 0,
       "avpe" : 0,
       "avdr" : 0,
       "avoq" : 0,
       "rvpe" : 0,
       "rvdr" : 0,
       "rvoq" : 0,
    }
   
    },
    computed: {
      totalPower() {
        // totalPower = ((avoq + avpe + reoq)/3)*0.76 + 40 + components;
        // totalDuration = ((0.4*avoq)+(0.6*avdr)+(0.4*reoq)+(0.6*redr))*6.5 + 1200;
        return ((this.avoq + this.avpe + this.rvoq)/3)*0.76 + 40 + (this.asds + this.acrm + this.abec);
      },
      totalDuration() {
        return ((0.4*this.avoq)+(0.6*this.avdr)+(0.4*this.rvoq)+(0.6*this.rvdr))*6.5 + 1200;
      }
  }

}
</script>

<style>
  img {
    height: 20px;  
  }
  form {
      background-color: #eee;
      border: 1px solid #ccc;
      display: grid;
      grid-gap: 5px;
      grid-template-columns: 1fr 1fr 3fr 1fr 3fr 1fr 3fr;
  }

  .subtitle {
    grid-column: 1 / 8;
    background-color: #ccc;
              
  }
  .last{
    //grid-column: 6 / 8;
  }
  
</style>
