<template>
	<div class="product">
		<ProductItem
			v-for="(item, index) in data"
			:key="index"
			:class="['productItem', { 'productItem-reverse': index % 2 !== 0 }]"
			:parent-data="item"
		/>
	</div>
</template>

<script>
	import ProductItem from "@/components/ProductItem";
	export default {
		name: "Product",
		data() {
			return {
				data: [],
			};
		},
		components: {
			ProductItem,
		},
		async created() {
			const api = "./data.json";
			try {
				const res = await this.$http.get(api);
				this.data = res.data;
			} catch (err) {
				console.log("獲取資料失敗:\n", err);
			}
		},
	};
</script>