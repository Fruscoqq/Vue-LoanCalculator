<template>
  <div id="test">
<h2>E-Z Loans</h2>

      <label>First name:</label><br>
      <input id="firstname" type="text" v-model="loanApp.firstName">
      <br> 
      <label>Last namee:</label><br>
      <input type="text" v-model="loanApp.lastName" id="lastname">
      <br>
      <label>Loan Period</label>
      <v-slider/>
      <input type="submit" id="submit" value="submit">
      <helper :object="loanApp"/>
      <button @click="backToBrief()" class="btn btn-primary">
      Back to intro & brief
    </button>
  </div>
</template>
<script>
import vSlider from "vue-slider-component";
import helper from "./helper";
export default {
  data() {
    return {
      loanApp: {
        firstName: "",
        lastName: "",
        loanPeriod: 0
      }
    };
  },
  components: {
    vSlider,
    helper
  },
  methods: {
    backToBrief() {
      this.$store.commit("toggleIntro");
    }
  }
};
</script>

<style lang="scss" scoped>

  body {
    background: red;
  }

  h2 {
    font-size: 18px;
    color: red;
  }

</style>