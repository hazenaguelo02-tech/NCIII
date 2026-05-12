<template>
  <v-container>

    <!-- HEADER -->

    <v-app-bar color="green"></v-app-bar>

    <!--BODY INCONTENT-->
    <v-row>
      <v-col>
        <h1>Products</h1>
        <p> browse Products</p>
      </v-col>
    </v-row>

    <!--item-->
    <v-row>
      <v-col cols="12" md="3" v-for="item in 5" :key="item">
        <v-card elevation="5">
          <v-img height="150"
          src="https://placehold.co/600x400?text=Product"
          cover
          >
          </v-img>
          <v-card-title>Mouse</v-card-title>
          <v-card-text>1500</v-card-text>
          <v-card-action>
            <v-btn color="red" variant="flat" block>Add to Cart</
              v-btn>
          </v-card-action>
        </v-card>
      </v-col>
    </v-row>


  </v-container>
</template>

<script lang="ts" setup>
//@ts-nocheck
const config = useRuntimeConfig();

// 1. Fetch products
async function fetchProducts() {
  try {

    const response =  await $fetch ("/api/products", {
      baseURL:"http://localhost:1337/"
    })

    console.log(response.data);
  } catch (err) {
    console.error("Failed to load Product")
  }
}

//2. Add to Cart

//3. submit order

// 4. Remove form Cart

onMounted(() => {fetchProducts} 
);

</script>

<style>

</style>