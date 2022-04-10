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
        <template #graphic>
          <Graphic :amounts="amounts" />
        </template>
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
import Graphic from "./Resume/Graphic.vue";

export default {
  components: {
    Layout,
    Header,
    Resume,
    Movements,
    Action,
    Graphic,
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
          amount: 100,
          time: new Date("04-01-2022"),
        },
        {
          id: 1,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 200,
          time: new Date("04-01-2022"),
        },
        {
          id: 2,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 500,
          time: new Date("04-01-2022"),
        },
        {
          id: 3,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 200,
          time: new Date("04-01-2022"),
        },
        {
          id: 4,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: -400,
          time: new Date("04-01-2022"),
        },
        {
          id: 5,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: -600,
          time: new Date("04-01-2022"),
        },
        {
          id: 6,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: -300,
          time: new Date("04-01-2022"),
        },
        {
          id: 7,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 0,
          time: new Date("04-01-2022"),
        },
        {
          id: 8,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 300,
          time: new Date("01-01-2022"),
        },
        {
          id: 9,
          title: "Movimiento",
          description: "Lorem ipsum dolor sit amet",
          amount: 500,
          time: new Date("01-01-2022"),
        },
      ],
    };
  },
  computed: {
    amounts() {
      const lastDays = this.movements
        .filter((m) => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);

          return m.time > oldDate;
        })
        .map((m) => m.amount);

      return lastDays.map((m, i) => {
        const lastMovements = lastDays.slice(0, i);
        return lastMovements.reduce((suma, movement) => {
          return suma + movement;
        }, 0);
      });
    },
  },
};
</script>
