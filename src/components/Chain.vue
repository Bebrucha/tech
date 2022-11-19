<script setup>
import { library } from "@fortawesome/fontawesome-svg-core";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { fab } from "@fortawesome/free-brands-svg-icons";
import { far } from "@fortawesome/free-regular-svg-icons";

import LineChart from "./Chainchart.vue";
library.add(fas, fab, far);
</script>

<template>
  <header>
    <h3 style="margin-bottom: 30px; margin-top: 20px">
      Chain gas tracker
      <font-awesome-icon icon="fa-solid fa-gas-pump" />
    </h3>
  </header>

  <main>
    <div class="row">
      <div
        class="card"
        style="
          width: 600px;
          height: 446px;
          box-shadow: 0px 0px 1px black;
          margin: auto;
        "
      >
        <div class="text-right text-muted">
          <small>
            Current date:
            {{ new Date().toLocaleString() }}
          </small>
          <font-awesome-icon
            icon="fa-brands fa-twitter"
            style="margin-left: 15px; margin-right: 15px; margin-top: 10px"
          />
        </div>

        <div class="card-group">
          <div class="card">
            <div class="card-body">
              <h5 class="text-center">
                <font-awesome-icon icon="fa-regular fa-smile" /> Low
              </h5>
              <h4 class="text-center text-success">8 gwei</h4>
              <p class="card-text text-center">
                <small class="text-muted">Base: 7 | Priority: 0</small>
                <br />
                <small class="text-muted">$0.14 | ~ 15 mins: 0 secs</small>
              </p>
            </div>
          </div>
          <div class="card">
            <div class="card-body">
              <h5 class="text-center">
                <font-awesome-icon icon="fa-regular fa-face-smile" /> Average
              </h5>
              <h4 class="text-center text-primary">10 gwei</h4>
              <p class="card-text text-center">
                <small class="text-muted">Base: 9 | Priority: 1</small>
                <br />
                <small class="text-muted">$0.16 | ~ 9 mins: 0 secs</small>
              </p>
            </div>
          </div>
          <div class="card">
            <div class="card-body">
              <h5 class="text-center">
                <font-awesome-icon icon="fa-regular fa-face-surprise" /> High
              </h5>
              <h4 class="text-center text-danger">12 gwei</h4>
              <p class="card-text text-center">
                <small class="text-muted">Base: 11 | Priority: 2</small>
                <br />
                <small class="text-muted">$0.19 | ~ 5 mins: 0 secs</small>
              </p>
            </div>
          </div>
        </div>

        <p style="font-weight: bold; margin-left: 10px; color: grey">
          Estimated Cost of Transaction Actions:
        </p>
        <div style="overflow-y: auto; margin-left: 10px; margin-right: 10px">
          <table class="table table-hover">
            <tr>
              <th>Action</th>
              <th>Low</th>
              <th>Average</th>
              <th>High</th>
            </tr>
            <tr>
              <td class="text-muted">Uniswap V3: Swap</td>
              <td>$1.99</td>
              <td>$2.17</td>
              <td>$3.42</td>
            </tr>
            <tr>
              <td class="text-muted">USDT: Transfer</td>
              <td>$1.96</td>
              <td>$2.66</td>
              <td>$2.67</td>
            </tr>
            <tr>
              <td class="text-muted">SushiSwap: Swap</td>
              <td>$3.50</td>
              <td>$4.88</td>
              <td>$4.90</td>
            </tr>
            <tr>
              <td class="text-muted">OpenSea: Sale</td>
              <td>$1.14</td>
              <td>$1.23</td>
              <td>$1.41</td>
            </tr>
            <tr>
              <td class="text-muted">Uniswap V3: Swap</td>
              <td>$2.94</td>
              <td>$3.17</td>
              <td>$3.62</td>
            </tr>
            <tr>
              <td class="text-muted">USDT: Transfer</td>
              <td>$0.86</td>
              <td>$0.93</td>
              <td>$1.06</td>
            </tr>
            <tr>
              <td class="text-muted">SushiSwap: Swap</td>
              <td>$2.25</td>
              <td>$2.43</td>
              <td>$2.77</td>
            </tr>
            <tr>
              <td class="text-muted">Curve: Swap</td>
              <td>$2.93</td>
              <td>$3.16</td>
              <td>$3.61</td>
            </tr>
            <tr>
              <td class="text-muted">Balancer: Swap</td>
              <td>$3.14</td>
              <td>$3.38</td>
              <td>$3.86</td>
            </tr>
          </table>
        </div>
      </div>
      <div
        class="card"
        style="
          width: 600px;
          height: 446px;
          box-shadow: 0px 0px 1px black;
          margin: auto;
        "
      >
        <div id="chart">
          <line-chart
            class="d-flex justify-content-center"
            style="margin-top: 20px"
          />
        </div>
      </div>
    </div>
  </main>
</template>
<style scoped>
.card-group {
  margin: 10px;
}
</style>
