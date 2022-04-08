<template>
	<div id="app">
		<header class="header">
			<h1 class="header__title">iPhone 機型</h1>
		</header>
    <main class="main container mx-auto">
      <Product />
    </main>
	</div>
</template>

<script>
  import Product from '@/components/Product'
	export default {
		name: "App",
		components: {
      Product,
    },
	};
</script>

<style lang="scss">
	.header {
    padding: {
      top: 48px;
      bottom: 48px;
    };
    text: {
      align: center;
    };
    &__title {
      font: {
        size: 3rem;
        weight: 700;
      };
    }
  }
</style>
