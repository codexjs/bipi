<template>
  <div id="carlist">
    <div class="car_list_header">
      <h1 class="list_title">Catálogo</h1>
      <CarListFilter />
    </div>
    <div class="card_container">
      <CarListCard v-for="car in data" :key="car.id" :query="{ id: car._id }" :data="car" />
    </div>
  </div>
</template>

<script>
import CarListCard from '../components/CarList/CarListCard.vue'
import CarListFilter from '../components/CarList/CarListFilter.vue'

export default {
  name: "CarList",
  components: {
    CarListCard,
    CarListFilter
  },
  data: () => ({
    group: null
  }),
  computed: {
    data(){
      return this.$store.state.cars
    }
  }
}
</script>

<style lang="scss">
#carlist {
  margin: 1em;
  margin-top: 5.5em;
}

.car_list_header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.list_title {
  font-size: 2.3em;
}

.card_container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
