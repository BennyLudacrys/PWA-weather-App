<template>
    <SearchComponentVue id="sc" :cidades="cidades" />
  <div id="div">
    <Card :dados="dados1" />
    <Card :dados="dados2" />
    <Card :dados="dados3" />
  </div>
  <Foot />
</template>

<script>
import SearchComponentVue from "./SearchComponent.vue";
import Card from "./Card.vue";
import Foot from "./Footer.vue";

export default {
  name: "MainPage",
  data() {
    return {
      cidades: ["Maputo","Xai-Xai","Inhambane","Beira","Chimoio","Tete","Quelimane","Nampula","Pemba",],
      dados1: [],
      dados2: [],
      dados3: [],
      interval: null,
      controlador: 0,
    };
  },
  components: {
    SearchComponentVue,
    Card,
    Foot,
  },

  methods: {
    renew() {
      if (this.controlador == 9) {
        this.controlador = 0;
        fetch(
          "https://api.openweathermap.org/data/2.5/weather?q=Lichinga,MZ&units=metric&APPID=1514774033ee4b35a27dea92bd4e45d9"
        )
          .then((resp) => resp.json())
          .then((data) => {
            this.dados1[0] = data.name;
            this.dados1[1] = data.main.temp_min;
            this.dados1[2] = data.main.temp_max;
            this.dados1[3] = data.weather[0].description;
          })
          .catch((err) => console.log(err));
      } else {
        this.controlador = this.controlador + 3;

        for (let a = this.controlador - 3; a < this.controlador; a++) {
          fetch(
            "https://api.openweathermap.org/data/2.5/weather?q=" +
              this.cidades[a] +
              ",MZ&units=metric&APPID=1514774033ee4b35a27dea92bd4e45d9"
          )
            .then((resp) => resp.json())
            .then((data) => {
              if (a == 0 || a == 3 || a == 6) {
                this.dados1[0] = data.name;
                this.dados1[1] = data.main.temp_min;
                this.dados1[2] = data.main.temp_max;
                this.dados1[3] = data.weather[0].description;
              } else if (a == 1 || a == 4 || a == 7) {
                this.dados2[0] = data.name;
                this.dados2[1] = data.main.temp_min;
                this.dados2[2] = data.main.temp_max;
                this.dados2[3] = data.weather[0].description;
              } else if (a == 2 || a == 5 || a == 8) {
                this.dados3[0] = data.name;
                this.dados3[1] = data.main.temp_min;
                this.dados3[2] = data.main.temp_max;
                this.dados3[3] = data.weather[0].description;
              }
            })
            .catch((err) => console.log(err));
        }
      }
    },
  },

  mounted() {
    // this.renew();
  },

  created() {
    this.interval = setInterval(() => {
      // this.renew();
    }, 2000);
  },
};
</script>

<style scoped>
#div {
  width: 100%;
  margin-top: 20px;
  display: flex;
  justify-content: space-evenly;
}

#sc{
  margin-top: 30px;
  width: 100%;
  display: flex;
  justify-content: center;
}

@media only screen and (max-width: 900px) {
  #div {
    justify-content: center;
    display: grid;
    grid-template-columns: 40% 40%;
  }
}

@media only screen and (max-width: 750px) {
  #div {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
}
</style>