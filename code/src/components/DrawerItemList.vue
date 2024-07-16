<script setup>
import { inject } from 'vue'
import DrawerItem from './DrawerItem.vue'

const { cart, removeFromCart } = inject('cart')
</script>

<template>
  <div class="flex flex-col gap-4" v-auto-animate>
    <DrawerItem
      v-for="item in cart"
      :key="item.id"
      :title="item.title"
      :price="item.price"
      :img-url="item.ImgUrl"
      @onClickRemove="() => removeFromCart(item)"
    />
  </div>
</template>
