<template>
  <v-container fill-height>
    <v-row justify="center">
      <v-col cols="12" sm="4" md="6">
        <CardTable :headers="headers" :offers="offers" :category="category" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import CardTable from "@/components/CardTable";
export default {
  name: "Offers",
  title: 'Offers',
  components: {
    CardTable
  },
  data: () => ({
    category: {
      name: "Offers",
      action: "Offer",
      color: "red accent-2"
    },

    headers: [
      {
        text: "Offers",
        sortable: false,
        value: "name"
      },
      { text: "Validity", sortable: false, value: "valid" }
    ],
    offers: [
      {
        name: "Offer #1",
        valid: "10th Jan"
      },
      {
        name: "Offer #2",
        valid: "15th Jan"
      },
      {
        name: "Offer #3",
        valid: "19th Jan"
      },
      {
        name: "Offer #4",
        valid: "15th Jan"
      },
      {
        name: "Offer #5",
        valid: "25th Jan"
      },
      {
        name: "Offer #6",
        valid: "15th Jan"
      },
      {
        name: "Offer #7",
        valid: "18th Jan"
      },
      {
        name: "Offer #8",
        valid: "5th Jan"
      },
      {
        name: "Offer #9",
        valid: "5th Feb"
      },
      {
        name: "Offer #10",
        valid: "15th March"
      }
    ]
  })
};
</script>
