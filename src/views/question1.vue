<template>
  <div>
    <!-- The original JSON array-->
    <div v-for="(customer, index) in originalCustomers" :key="'original'+index">
      {{customer}}
    </div>

    <br><br>

    <!-- Sort the JSON array and print out the sentence-->
    <div v-for="(customer, index) in (customers)" :key="'sort'+index">
      <!-- First Letter Uppercase function-->
      {{firstLetterUppercase(customer.name)}} want to buy
      <template v-for="(car, carIndex) in customer.cars">
        <template v-if="customer.cars.length > 1 && customer.cars.length !== carIndex+1">
          {{car}},
        </template>
        <template v-else>
          {{car}}
        </template>
      </template>
    </div>
  </div>
</template>

<script>
  export default {
    name: "question1",
    data() {
      return {
        // The original JSON array
        originalCustomers: [
          {
            name: "rick",
            cars: ["Corvette Z06", "Lotus Exite S"],
          },
          {
            name: "john",
            cars: ["BMW 320D"],
          },
          {
            name: "zing",
            cars: ["​Honda Jazz", "Honda Click", "Honda Waves"],
          }
        ],
        customers: [
          {
            name: "rick",
            cars: ["Corvette Z06", "Lotus Exite S"],
          },
          {
            name: "john",
            cars: ["BMW 320D"],
          },
          {
            name: "zing",
            cars: ["​Honda Jazz", "Honda Click", "Honda Waves"],
          }
        ],
      }
    },
    methods: {
      sortCustomers: (customers) => {
        // Sort ascending.
        return customers.sort((a, b) => {
          // Sort number of cars in customers.
          return a.cars.length - b.cars.length
        });
      },
      firstLetterUppercase(string) {
        // Make the first letter of string to uppercase.
        return string.charAt(0).toUpperCase() + string.slice(1);
      }
    },
    created() {
      this.customers = this.sortCustomers(this.customers)
    }
  }
</script>

<style scoped>

</style>