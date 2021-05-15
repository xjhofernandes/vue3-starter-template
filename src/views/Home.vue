<template>
  <div class="container">
    <section>
      <div class="is-flex level">
        <div class="is-flex">
          <p class="is-size-3">Dashboard:</p>
          <p class="is-size-5">Charactere Tracking</p>
        </div>
        <div>
          <a>
            <BruxoIcon class="icon" />
          </a>
        </div>
          <div class="field is-horizontal">
            <div class="field-label is-normal">
              <label class="label">Gold</label>
            </div>
            <div class="field-body">
              <div class="field">
                <div class="control has-icons-right">
                  <input class="input" type="text" value="1.579.574" readonly>
                  <span class="icon is-small is-right">
                    <i class="fas fa-check"> teste</i>
                  </span>                  
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
import BruxoIcon from "../assets/icons/coin.svg"

export default {
  components: {
    BruxoIcon
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