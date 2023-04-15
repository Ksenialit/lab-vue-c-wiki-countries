<template>
    <div class="col-7">
            <img src="https://restcountries.eu/data/fra.svg" alt="country flag" style="width: 300px"/>
            <h1>{{  }}</h1>
            <table class="table">
              <thead></thead>
              <tbody>
                <tr>
                  <td style="width: 30%">Capital</td>
                  <td>{{ }}</td>
                </tr>
                <tr>
                  <td>Area</td>
                  <td>
                    {{ }} km <sup>2</sup>
                  </td>
                </tr>
                <tr>
                  <td>Borders</td>
                  <td>
                    <ul>
                      <li>
                        <router-link href=""> {{  }}</router-link>
                      </li>
                    </ul>  
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
</template>

<script>
    export default {
        name: "CountryDetails"
    }
</script>

<style scoped>

</style>