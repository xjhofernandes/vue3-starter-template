<template>
  <div class="container">
    <section>
      <div class="is-flex level">
        <div class="is-flex">
          <p class="is-size-4 has-text-white">Dashboard:</p>
          <p class="ml-4 is-size-4 has-text-grey-light">Character Tracking</p>
        </div>
        <div>
            <BruxoIcon class="icon is-large"/>
            <!-- <img src="@/assets/icons/bruxo.svg" alt="Kiwi standing on oval"> -->
        </div>
          <div class="field is-horizontal">
            <div class="field-label is-normal">
              <label class="label is-size-4 has-text-grey-light">Gold</label>
            </div>
            <div class="field-body">
              <div class="field">
                <div class="control has-icons-right is-inline">
                  <input class="input" type="text" value="1.579.574" readonly>
                  <MoedaIcon class="icon is-small is-size-7 is-right"/>
                </div>
              </div>
            </div>
          </div>    
      </div>
      <div class="columns">
        <div class="column is-12">
            <table class="table is-fullwidth">
                <tr>
                  <th>Name</th>
                  <th>Class</th>
                  <th>Level</th>
                  <th>Job</th>
                  <th>Power</th>
                  <th>Magic Power</th>
                  <th>Defense</th>
                </tr>
                <tr v-for="colunas in heroAttributes" :key="colunas">
                  <td v-for="coluna in colunas" :key="coluna"> {{ coluna }}</td>
                </tr>
              </table>
        </div>
      </div>
    </section>


  </div>
</template>

<script>
import BruxoIcon from "@/assets/icons/bruxo.svg"
import MoedaIcon from "@/assets/icons/coin.svg"

export default {
  components: {
    BruxoIcon,
    MoedaIcon
  },
  data() {
    return {
      heroAttributes: [{
        "name": "Anferus",
        "class": "Mage",
        "level": 42,
        "job": 34,
        "power": 17,
        "magic_power": 70,
        "defense": 25
      }],
    };
  },
};
</script>

<style scoped>
/* .default-background-color{
  color: #has-text-white;
} */
</style>