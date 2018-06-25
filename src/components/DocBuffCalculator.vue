<template>
    <div>
      <form class="form1" action="">
        <label class="subtitle"><h3>Buff Crafting Calculator</h3></label>
        <label for="asds">Component Power</label>
        <label for="asds" title="Advanced ">ASDS</label>
        <input id="asds" v-model.number="asds" type="number">

        <label for="acrm">ACRM</label>
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
        <label class="subtitle"><p><strong>Power:</strong> {{ totalPower }} </p>
        <p><strong>Duration:</strong> {{ totalDuration }} </p></label>
        </form>
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
        return Math.round(((this.avoq + this.avpe + this.rvoq)/3)*0.76 + 40 + (this.asds + this.acrm + this.abec));
      },
      totalDuration() {
        return Math.round(((0.4*this.avoq)+(0.6*this.avdr)+(0.4*this.rvoq)+(0.6*this.rvdr))*6.5 + 1200);
      }
  }

}
</script>

<style>
  * {
    color: #c8f4f3;
  }
  body, input {
    background-color: #003344;
    
  }
  input {
    width: 50px;
    padding: 3px;
    margin: 0;
    height: 20px;
    border: 1px solid #006b87;
  }
  img {
    height: 20px;  
  }
  form {
      width: 780px;   
      background-color: #589bac;
      border: 1px solid #05fffe;
      display: grid;
      grid-gap: 10px;
      grid-template-columns: 1fr 1fr 3fr 1fr 3fr 1fr 3fr;
      padding: 5px;
      -moz-border-radius: 5px;
      -webkit-border-radius: 5px;
      border-radius: 5px; /* future proofing */
      -khtml-border-radius: 5px; /* for old Konqueror browsers */
  }

  .subtitle {
    background-color: #006b87;
    grid-column: 1 / 8;
    -moz-border-radius: 5px;
    -webkit-border-radius: 5px;
    border-radius: 5px; /* future proofing */
    -khtml-border-radius: 5px; /* for old Konqueror browsers */
                 
  }
  
</style>
