<template>
  <div class="form-group">
    <select class="form-control" @change="changeEsp($event)">
      <option value="" selected disabled>Sélectionner un ESP</option>
      <option v-for="esp in espList" :key="esp.mac" :id="esp.mac">{{ esp.name }}</option>
    </select>
    <br><br>
    <p><span>Nom: <b>{{ selectedEsp.name }}</b></span></p>
    <p><span>Adresse IP: <b>{{ selectedEsp.ip }}</b></span></p>
    <p><span>Adresse MAC: <b>{{ selectedEsp.mac }}</b></span></p>
    <p><span>Led allumée: <b>{{ selectedEsp.led }}</b></span></p>
    <p><span>Luminosité détectée: <b>{{ selectedEsp.light }}</b></span></p>
  </div>
</template>

<script>

export default {
  name: "EspSelector",
  data: function () {
    return {
      selectedEsp: [{}],
      espList: [{}]
    }
  },
  methods: {
    changeEsp (event) {
        this.selectedEsp = this.espList.find(esp => esp.mac === event.target.options[event.target.options.selectedIndex].id);
    }
  },
  async created () {
    const response = await fetch("http://34.212.75.109:3000/esp");
    this.espList = await response.json();
  },
}



</script>

<style scoped>

</style>