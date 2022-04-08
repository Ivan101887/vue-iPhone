<template>
  <section class="shopItem">
    <div class="shopItem__info">
      <h2 class="shopItem__title"> {{ parentData.name }} </h2>
      <p class="shopItem__pubYear">推出年份：{{new Date(parentData.date).getFullYear()}} 年</p>
      <p class="shopItem__capacity">
        容量：
        <span 
          class="shopItem__opts"
          v-for="item in parentData.capacity" 
          :key="item"
        >{{item}}</span>
      </p>
    </div>
    <figure class="shopItem__imgWrap">
      <img 
        :src="parentData.src" 
        :alt="parentData.name" 
        class="shopItem__img"
        width="956"
        height="700">
    </figure>
  </section>
</template>

<script>
export default {
  name: 'IPhone',
  props: {
    parentData: Object, 
  },
  
}
</script>

<style lang="scss" scoped>
  .shopItem {
    padding: {
      top: 80px;
      bottom: 70px;
    };
    &__opts + &__opts::before {
      content: "";
      
    }
  }
</style>