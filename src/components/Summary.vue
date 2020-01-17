<template>
  <v-container fill-height>
    <v-row>
      <v-col cols="12" md="4">
        <Card :type="offers" />
      </v-col>
      <v-col cols="12" md="4">
        <Card :type="incomes" />
      </v-col>
      <v-col cols="12" md="4">
        <Card :type="outcomes" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Card from "@/components/Card";
export default {
  name: "Summary",
  components: {
    Card
  },
  data: () => ({
    offers: {
      title: "Offers",
      list: ["Offer #1", "Offer #2", "Offer #3"],
      items: ["Add Offer", "Show All"]
    },
    incomes: {
      title: "Incomes",
      list: ["Income #1", "Income #2", "Income #3"],
      items: ["Add Income", "Show All"]
    },
    outcomes: {
      title: "Outcomes",
      list: ["Outcome #1", "Outcome #2", "Outcome #3"],
      items: ["Add Outcome", "Show All"]
    }
  })
};
</script>
