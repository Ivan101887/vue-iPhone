<template>
	<div class="shopItems">
		<IPhone 
      v-for="(item, index) in data" :key="index" 
      :class="[ index % 2 === 0 ? 'd-flex' : 'd-flex d-flex--reverse']"
      :parent-data="item" 
    >{{item}}</IPhone>
	</div>
</template>

<script>
  import IPhone from '@/components/IPhone'
	export default {
		name: "Commodities",
    data(){
      return {
        data: [],
      };
    },
		components: {
      IPhone,
    },
		async created() {
			const api = "./data.json";
			try {
				const res = await this.$http.get(api);
				this.data = res.data;
        console.log(this.data)
			} catch (err) {
				console.log("獲取資料失敗:\n", err);
			}
		},
	};
</script>