<template>
  <div class="container">
    <h5>Accounts</h5>
    <table class="table">
    <thead>
      <tr>
        <th>Account</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="account in accounts" v-bind:key="account.id">
        <td>{{account.name}}</td>
      </tr>
    </tbody>
    </table>
  </div>
</template>

<script>
// Import utils from YNAB
import {utils} from 'ynab';

export default {
  props: ['accounts'],
  methods: {
    // Now we can make this method available to our template
    // So we can format this milliunits in the correct currency format
    convertMilliUnitsToCurrencyAmount: utils.convertMilliUnitsToCurrencyAmount
  }
}
</script>
