<script setup>
import { library } from "@fortawesome/fontawesome-svg-core";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { fas } from "@fortawesome/free-solid-svg-icons";
import { fab } from "@fortawesome/free-brands-svg-icons";
import { far } from "@fortawesome/free-regular-svg-icons";

library.add(fas, fab, far);
</script>

<script>
import Ethereum from "./components/Ethereum.vue";
import Binance from "./components/Binance.vue";
import Polygon from "./components/Polygon.vue";

const routes = {
  "/": Ethereum,
  "/binance": Binance,
  "/polygon": Polygon,
};

export default {
  data() {
    return {
      currentPath: window.location.hash,
    };
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || "/"] || Ethereum;
    },
  },
  mounted() {
    window.addEventListener("hashchange", () => {
      this.currentPath = window.location.hash;
    });
  },
};
</script>
<template>
  <h3
    class="d-flex justify-content-center"
    style="margin-bottom: 30px; margin-top: 20px"
  >
    Crypto networks
  </h3>
  <header>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bootstrap@4.0.0/dist/css/bootstrap.min.css"
      integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
      crossorigin="anonymous"
    />
    <div
      class="card"
      style="
        width: 1220px;
        height: 150px;
        box-shadow: 0px 0px 1px black;
        margin: auto;
      "
    >
      <div class="d-flex flex-row d-flex justify-content-around">
        <div class="d-flex flex-column">
          <img
            src="./assets/ether.png"
            style="
              height: 50px;
              width: 50px;
              margin-top: 20px;
              margin-left: 20px;
            "
          />
          <br />
          <button class="btn btn-primary">
            <a href="#/" class="text-white">Ethereum</a>
          </button>
        </div>
        <div class="d-flex flex-column">
          <img
            src="./assets/binance_logo.png"
            style="
              height: 50px;
              width: 50px;
              margin-top: 20px;
              margin-left: 56px;
            "
          />
          <br />
          <button class="btn btn-primary">
            <a href="#/binance" class="text-white">Binance smart chain</a>
          </button>
        </div>
        <div class="d-flex flex-column">
          <img
            src="./assets/polygon.png"
            style="
              height: 50px;
              width: 50px;
              margin-top: 20px;
              margin-left: 15px;
            "
          />
          <br />
          <button class="btn btn-primary">
            <a href="#/polygon" class="text-white">Polygon</a>
          </button>
        </div>
      </div>
    </div>
  </header>

  <main>
    <component :is="currentView" />
  </main>
</template>

<style scoped>
.card-group {
  margin: 10px;
}
</style>
