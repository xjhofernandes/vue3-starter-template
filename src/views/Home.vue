<template>
  <div class="container p-5">
    <section>
      <div class="is-flex level">
        <div class="is-flex">
          <p class="is-size-4 has-text-white">Dashboard:</p>
          <p class="ml-4 is-size-4 has-text-grey-light">Character Tracking</p>
        </div>
        <div>
          <BruxoIcon class="icon" style="height: 6rem; width: 6rem" />
        </div>
        <div class="field is-horizontal">
          <div class="field-label">
            <label class="is-size-4 has-text-grey-light">Gold</label>
          </div>
          <div class="field-body">
            <div class="field">
              <div class="control has-icons-right is-inline">
                <input class="input" type="text" value="1.579.574" readonly />
                <MoedaIcon
                  class="icon is-small is-size-7 is-right mr-2"
                  style="opacity: 0.2"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="columns">
        <div class="column is-12">
          <table class="table is-fullwidth">
            <tr style="background-color: #85c1e9">
              <th
                class="has-text-white"
                v-for="colunas in Object.keys(heroAttributes[0])"
                :key="colunas"
              >
                {{ colunas }}
              </th>
            </tr>
            <tr v-for="colunas in heroAttributes" :key="colunas">
              <td v-for="coluna in colunas" :key="coluna">{{ coluna }}</td>
            </tr>
          </table>
        </div>
      </div>
    </section>

    <section>
      <div class="columns">
        <div class="column is-12">
          <div class="is-flex">
            <p class="is-size-4 has-text-white">teste:</p>
            <p class="is-size-4 has-text-grey-light">teste</p>
          </div>
        </div>
      </div>
      <div class="columns">
        <div class="column is-6">
          <DashboardChart
            :chart_height="550"
            :chart="trace2"
            :xaxis_dtick="10800000"
          />
        </div>
        <div class="column is-6">
          <DashboardChart
            :chart_height="550"
            :chart="trace1"
            :xaxis_dtick="10800000"
          />
        </div>        
      </div>
    </section>
  </div>
</template>

<script>
import BruxoIcon from "@/assets/icons/bruxo.svg";
import MoedaIcon from "@/assets/icons/coin.svg";
import DashboardChart from "@/components/DashboardChart.vue";

export default {
  components: {
    BruxoIcon,
    MoedaIcon,
    DashboardChart,
  },
  data() {
    return {
      heroAttributes: [
        {
          Name: "Anferus",
          Class: "Mage",
          Level: 42,
          Job: 34,
          Power: 17,
          "Magic Power": 70,
          Defense: 25,
        },
      ],
      trace1: {
        uuid: "grafico-teste",
        traces: [
          {
            type: "bar",
            name: "grade",
            x: [1, 2, 3, 4],
            y: [5, 10, 2, 8],
            marker: {
              color: "#85c1e9",
            },
          },
        ],
      },    
      trace2: {
        uuid: "grafico-teste",
        traces: [
          {
            type: "bar",
            name: 'LA Zoo',
            x: ['giraffes', 'orangutans', 'monkeys'],
            y: [20, 14, 23],
            marker: {
              color: "#1a5276",
            },
          },
          {
            type: "bar",
            name: 'LA Zoo',
            x: ['giraffes', 'orangutans', 'monkeys'],
            y: [5, 10, 2],
            marker: {
              color: "#85c1e9",
            },
          },          
        ],
      },        
    };
  },
};
</script>

<style scoped>
/* .default-background-color{
  color: #has-text-white;
} */
</style>