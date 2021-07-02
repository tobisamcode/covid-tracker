<template>
  <main v-if="!loading">
    Show data
  </main>

  <main class="flex flex-col justify-center text-center align-center" v-else>
  <div class="mt-10 mb-6 text-3xl text-gray-500">Fetching Data</div>
  <img :src="loadingImage" class="w-24 m-auto" alt="">
  </main>
</template>

<script>


export default {
  name: 'Home',
  components: {},
  data () {
    return {
      loading: true,
      title: 'Global',
      dataDate: '',
      stats: {},
      countries: [],
      loadingImage: require('../assets/Spinner-3.gif')
    }
  },
  methods: {
    async fetchCovidData(){
      const res = await fetch('https://api.covid19api.com/summary')
      const data = await res.json()
      return data
    }
  },
  async created (){
    const data = await this.fetchCovidData()
    
    this.dateDate = data.Date
    this.stats = data.Global
    this.countries = data.Countries
    this.loading = true
  },
}
</script>
