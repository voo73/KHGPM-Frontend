<template>
  <div>
    <h3>판매상품</h3>
    <table>
        <tr>
            <th align="center" width="100">No</th>
            <th align="center" width="300">상품명</th>
            <th align="center" width="200">상품가격</th>
            <th align="center" width="100">작성자</th>
            <th align="center" width="100">등록일자</th>
        </tr>
        <tr v-if="!products || (Array.isArray(products) && products.length===0)">
          <td colspan="5">
              현재 판매중인 상품이 없습니다. 
          </td>
        </tr>
        <tr v-else v-for="product in products" :key="product.productNo">
          <td align="center">
            {{ product.productNo }}
          </td>
          <td align="center">
            {{ product.productName }}
          </td>
          <td align="center">
            {{ product.price }}
          </td>
          <td align="center">
            {{ product.writer }}
          </td>
          <td align="center">
            {{ product.regDate }}
          </td>
        </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "JspProductList",
  props: {
    products:{
      type: Array
    }
  }
}
</script>

<style>

</style>