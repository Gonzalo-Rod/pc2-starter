<script>
export default {
  name: "CountryComponent",
  props: [
    "name",
    "capital",
    "currency_name",
    "currency",
    "region",
    "code",
    "click",
  ],
};
</script>

<template>
  <p class="country-hover">{{ click }}</p>
  <p
    @click="this.$router.push({ path: `/countries/${code}` })"
    class="country-hover"
    >
  </p>
  <div>
  <img
      width="200"
      height="200"
      :src="`https://countryflagsapi.com/png/${code}`" 
    />
    <h1>{{ name }}</h1>
    <h2>{{ capital }}</h2>
    <h3>{{ currency_name }}</h3>
    <h4>{{ region }}</h4>
  </div>
</template>

<style scoped>
.country {
  padding: 2px;
  white-space: nowrap;
  width: 350px;
  height: 350px;
  border-style: solid;
  border-radius: 5px;
  border-color: grey;
}

.country-hover:hover {
  background-color: rgb(49, 49, 49);
  cursor: pointer;
}

h1 {
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
