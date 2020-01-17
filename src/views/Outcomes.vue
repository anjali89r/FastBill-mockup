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
  name: "Outcomes",
  title: 'Outcomes',
  components: {
    CardTable
  },
  data: () => ({
    category: {
      name: "Outcomes",
      action: "Outcome",
      color: "deep-orange lighten-1"
    },

    headers: [
      {
        text: "Outcomes",
        sortable: false,
        value: "name"
      },
      { text: "Validity", sortable: false, value: "valid" }
    ],
    offers: [
      {
        name: "Outcome #1",
        valid: "10th Jan"
      },
      {
        name: "Outcome #2",
        valid: "15th Jan"
      },
      {
        name: "Outcome #3",
        valid: "19th Jan"
      },
      {
        name: "Outcome #4",
        valid: "15th Jan"
      },
      {
        name: "Outcome #5",
        valid: "25th Jan"
      },
      {
        name: "Outcome #6",
        valid: "15th Jan"
      },
      {
        name: "Outcome #7",
        valid: "18th Jan"
      },
      {
        name: "Outcome #8",
        valid: "5th Jan"
      },
      {
        name: "Outcome #9",
        valid: "5th Feb"
      },
      {
        name: "Outcome #10",
        valid: "15th March"
      }
    ]
  })
};
</script>

