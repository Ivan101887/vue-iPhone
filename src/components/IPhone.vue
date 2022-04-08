<template>
	<section class="shopItem">
		<div class="shopItem__info">
			<h2 class="shopItem__name">{{ parentData.name }}</h2>
			<p class="shopItem__pubYear">
				推出年份：{{ new Date(parentData.date).getFullYear() }} 年
			</p>
			<p class="shopItem__capacity">
				容量：
				<span
					class="shopItem__opts"
					v-for="item in parentData.capacity"
					:key="item"
				>
					{{ item }}
				</span>
			</p>
			<p class="shopItem__color">
				顏色：
				<span
					class="shopItem__opts"
					v-for="item in parentData.color"
					:key="item"
				>
					{{ item }}
				</span>
			</p>
			<p class="shopItem__model">
				型號：
				<span
					class="shopItem__opts"
					v-for="item in parentData.model"
					:key="item"
				>
					{{ item }}
				</span>
			</p>
			<p class="shopItem__note">{{ parentData.note }}</p>
      <p class="shopItem__quote">
        請參閱
        <a 
          class="shopItem__link"
          :href="parentData.link" 
        >{{parentData.name}} 技術規格</a>
      </p>
		</div>
		<figure class="shopItem__imgWrap">
			<img
				:src="parentData.src"
				:alt="parentData.name"
				class="shopItem__img"
				width="956"
				height="700"
			/>
		</figure>
	</section>
</template>

<script>
	export default {
		name: "IPhone",
		props: {
			parentData: Object,
		},
	};
</script>

<style lang="scss" scoped>
	.shopItem {
		padding: {
			top: 70px;
			bottom: 70px;
		}
    margin: {
      left: -15px;
      right: -15px;
    };
    border: {
      bottom: 1px solid #ccc
    };
    align-items: center;
    &__name {
      font: {
        size: 30px;
        weight:600;
      };
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
      };
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
        size: 16px
      }
      line-height: 1.75em;
    }
    &__model {
      margin: {
        bottom: 20px;
      }
    }
    &__note {
      line-height: 1.75em;
      color: #666;
      font: {
        size: 0.934rem;
      };
      margin: {
        bottom: 25px;
      };
    }
    &__quote {
      font: {
        size: 0.934rem;
      }
      color: #666;
    }
    &__link {
      color: #007AFE;
    };
		
		&__opts + &__opts::before {
			content: "、";
		}
	}
</style>