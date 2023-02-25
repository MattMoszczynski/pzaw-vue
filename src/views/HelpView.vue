<script>
import HelloWorld from '../components/HelloWorld.vue';
import Button from 'primevue/button';
import TabView from 'primevue/tabview';
import TabPanel from 'primevue/tabpanel';

export default {
  components: { HelloWorld, Button, TabView, TabPanel },
  data() {
    return {
      message: "Pomocna strona",
      user: {}
    }
  },
  mounted() {
    this.axios.get(`https://api.github.com/users/MattMoszczynski`)
      .then(response => {
          this.user = response.data
      })

    this.$toast.add({severity:'success', summary: 'Prime działa!', detail:'Wyszukaj mnie po tytule żeby wyłączyć ten komunikat, albo odczekaj 10 sekund :)', life: 10000});
  }
}
</script>

<template>
  <main>
    <h1>Trochę tu nieład ale przedstawiam najważniejsze informacje:</h1>

    <h2>1. Przykład zaimportowania komponentu z podpięciem wartości</h2>
    <HelloWorld :msg="message"/>

    <br><br><br>

    <h2>2. Przykład zaimportowania komponentu Prime Vue</h2>
    <Button label="Testowy przycisk"/>
    <TabView>
      <TabPanel header="Strona 1">
        Treść 1...
      </TabPanel>
      <TabPanel header="Strona 2">
        Treść 2...
      </TabPanel>
      <TabPanel header="Strona 3">
        Treść 3...
      </TabPanel>
    </TabView>

    <br><br><br>

    <h2>3. Lista kontrolek/komponentów Prime Vue</h2>
    <a
      href="https://primevue.org/icons"
      target="_blank"
      rel="noopener noreferrer"
    >
      Kliknij tu
    </a>

    <br><br>

    <i class="pi pi-check"></i>
    <i class="pi pi-times"></i>
    <i class="pi pi-cloud"></i>
    <i class="pi pi-sun"></i>

    <br><br><br>

    <h2>4. Lista ikonek Prime Vue oraz ich użycie</h2>
    <a
      href="https://primevue.org/setup"
      target="_blank"
      rel="noopener noreferrer"
    >
      Kliknij tu
    </a>



    <br><br><br>

    <h2>5. Przykład pobrania danych za pomocą Axiosa:</h2>
    {{ user }}

    <br><br><br>

  </main>
</template>
