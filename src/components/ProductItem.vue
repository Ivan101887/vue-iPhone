<template>
	<section>
		<div class="productItem__info">
			<h2 class="productItem__name">{{ parentData.name }}</h2>
			<p class="productItem__pubYear">
				推出年份：{{ new Date(parentData.date).getFullYear() }} 年
			</p>
			<p class="productItem__capacity">
				容量：{{ joinArray(parentData.capacity) }}
			</p>
			<p class="productItem__color">
				顏色：{{ joinArray(parentData.color) }}
			</p>
			<p class="productItem__model">
				型號：{{ joinArray(parentData.model) }}
			</p>
			<p class="productItem__note">{{ parentData.note }}</p>
			<p class="productItem__quote">
				請參閱
				<a 
          class="productItem__link" 
          :href="parentData.link"
				>{{ parentData.name }} 技術規格</a
				>
			</p>
		</div>
		<figure class="productItem__imgWrap">
			<img
				:src="parentData.src"
				:alt="parentData.name"
				class="productItem__img"
				width="956"
				height="700"
			/>
		</figure>
	</section>
</template>

<script>
	export default {
		name: "productItem",
		props: {
			parentData: Object,
		},
		methods: {
			joinArray(arr) {
				return arr.join('、');
			},
		},
	};
</script>

<style lang="scss" scoped>
	.productItem {
    display: flex;
		padding: {
			top: 70px;
			bottom: 70px;
		}
		margin: {
			left: -15px;
			right: -15px;
		}
		border: {
			bottom: 1px solid #ccc;
		}
		align-items: center;
    &-reverse {
      flex: {
        direction: row-reverse;
      };
    }
		&__name {
			font: {
				size: 30px;
				weight: 700;
			}
			margin: {
				bottom: 30px;
			}
		}
		&__info,
		&__imgWrap {
			width: 50%;
			margin: {
				left: 15px;
				right: 15px;
			}
		}
		&__img {
			display: block;
			width: 100%;
			height: auto;
		}
		&__pubYear,
		&__capacity,
		&__color,
		&__model {
			font: {
				size: 16px;
			}
			line-height: 1.65em;
		}
		&__model {
			margin: {
				bottom: 10px;
			}
		}
		&__note {
			line-height: 1.75em;
			color: #666;
			font: {
				size: 0.934rem;
			}
			margin: {
				bottom: 20px;
			}
			text-align: jusify;
		}
		&__quote {
			font: {
				size: 0.934rem;
			}
			color: #666;
		}
		&__link {
			color: #007afe;
		}
	}
</style>