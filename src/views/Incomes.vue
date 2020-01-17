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
  name: "Incomes",
  title: 'Incomes',
  components: {
    CardTable
  },
  data: () => ({
    category: {
      name: "Incomes",
      action: "Income",
      color: "teal"
    },

    headers: [
      {
        text: "Incomes",
        sortable: false,
        value: "name"
      },
      { text: "Validity", sortable: false, value: "valid" }
    ],
    offers: [
      {
        name: "Income #1",
        valid: "10th Jan"
      },
      {
        name: "Income #2",
        valid: "15th Jan"
      },
      {
        name: "Income #3",
        valid: "19th Jan"
      },
      {
        name: "Income #4",
        valid: "15th Jan"
      },
      {
        name: "Income #5",
        valid: "25th Jan"
      },
      {
        name: "Income #6",
        valid: "15th Jan"
      },
      {
        name: "Income #7",
        valid: "18th Jan"
      },
      {
        name: "Income #8",
        valid: "5th Jan"
      },
      {
        name: "Income #9",
        valid: "5th Feb"
      },
      {
        name: "Income #10",
        valid: "15th March"
      }
    ]
  })
};
</script>
