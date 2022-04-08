<template>
  <Layout>
    <template #header>
      <Header />
    </template>
    <template #resume>
      <Resume
        :label="label"
        :date="'06 de Abril 2022'"
        :total-amount="100000"
        :amount="amount"
      >
        <template #graphic> graphic </template>
        <template #action>
          <Action />
        </template>
      </Resume>
    </template>
    <template #movements>
      <Movements :movements="movements" />
    </template>
  </Layout>
</template>

<script>
import Layout from "./Layout.vue";
import Header from "./Header.vue";
import Resume from "./Resume/Index.vue";
import Movements from "./Movements/Index.vue";
import Action from "./Action.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
    Action,
  },
  data() {
    return {
      amount: null,
      label: null,
      movements: [
        {
          id: 0,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 1,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: -1000,
        },
        {
          id: 2,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 3,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: -1000,
        },
        {
          id: 4,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 5,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 6,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 7,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 8,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
        {
          id: 9,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 1000,
        },
      ],
    };
  },
};
</script>
