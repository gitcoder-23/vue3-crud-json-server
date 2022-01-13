<template>
  <tr v-for="(productData, index) in allProducts" :key="productData.id">
    <td>{{ index + 1 }}</td>
    <td>{{ productData.id }}</td>
    <td>{{ productData.title.substring(0, 45) }}...</td>
    <td>
      <img :src="productData.image" :alt="productData.title" width="90" />
    </td>
    <td>
      <router-link
        :to="{ name: 'EditProduct', params: { proId: productData.id } }"
        class="btn"
        >Edit</router-link
      >
      <button
        class="btn btn-del"
        type="button"
        @click="delProduct(productData.id)"
      >
        Delete
      </button>
    </td>
  </tr>
  <!-- <button @click="('setTitle')">Set Title</button> -->
  <p style="text-align: center">{{ listTitle }} <br /><br />{{ listName }}</p>
</template>

<script>
export default {
  name: 'ChildProducts',
  props: ['listTitle', 'listName', 'allProducts', 'delProduct'],
  // setup(props) {
  //   const setTitle = () => {
  //     console.log('yes');
  //     $emit('changeTitle', 'code test data!');
  //     console.log('yes');
  //   };
  //   return { setTitle };
  // },
};
</script>

<style></style>
