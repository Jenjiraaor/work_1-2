<template>
 <div>
  <v-carousel hide-controls>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
     </v-carousel>
    <nuxt-link to="/table"><center><h1>รายละเอียดสินค้า</h1></center></nuxt-link><br> 
   </div>
</template>
<script>
  export default {
    data () {
      return {
        items: [
          {
            src: '/image/3b.jpg'
          },
          {
            src: '/image/a.jpg'
          },
        ]
      }
    }
  }
</script>