<template>
		<div class="th-sticky_wrap">
			<table class="st-tbl1">
				<thead>
					<tr>
						<th>コード</th>
						<th>名称</th>
						<th>カテゴリ</th>
					</tr>
				</thead>
				<tbody>
					<tr v-for="(goods) in goodsList" v-bind:key="goods.code">
						<td>{{ goods.code}}</td>
						<td>{{ goods.name }}</td>
						<td>{{ goods.category }}</td>
					</tr>
				</tbody>
			</table>
		</div>
		
</template>

<script>
import * as axios from 'axios'

export default {
  components: {
  },
  name: 'GoodsList',
  data: () => ({
	goodsList: []
	}),
  mounted () {
	axios.get('/goods/list')
      .then(response => {
        this.goodsList = response.data
    })
  }
}
</script>