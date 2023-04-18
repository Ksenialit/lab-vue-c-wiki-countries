<template>
  <div class="col-7">
    <img :src="`https://flagcdn.com/${country.alpha2Code.toLowerCase()}.svg`" alt="country flag" style="height: 150px"/>
    <h1>{{country.name.common}}</h1>
    <table class="table">
      <thead></thead>
      <tbody>
        <tr>
          <td style="width: 30%">Capital</td>
          <td>{{country.capital[0]}}</td>
        </tr>
        <tr>
          <td>Area</td>
          <td>
            {{country.area}} km <sup>2</sup>
          </td>
        </tr>
        <tr>
          <td>Borders</td>
          <td>
            <ul v-for="border in bordersName" :key="bordersName.id">
              <li><router-link :to="`/list/${border.code}`">{{ border.name }}</router-link></li>
            </ul>  
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
    import countries from "../countries.json"

    export default {
        name: "CountryDetails",
        created() {
          this.$watch(
            () => this.$route.params.alpha3Code,
            () => {
              this.country = this.getCountry()
              this.bordersName = this.getBordersName()
            }
          )
        },
        data() {
            return {
              country: this.getCountry(),
              bordersName: this.getBordersName()
            }
        },
        methods: {
          getCountry() {
            let alpha3Code = this.$route.params.alpha3Code
            let country = countries.find(element => element.alpha3Code === alpha3Code)
            return country
          },
          getBordersName() {
            let country = this.getCountry()
            let borders = country.borders
            let bordersList = borders.map(border => {
              let country = countries.find(country => country.alpha3Code === border)
              return {
                name: country.name.common,
                code: country.alpha3Code,
                id: country._id
              }
            })
            return bordersList
          }
        }
    }
</script>

<style scoped>

</style>