<template>
  <div class="animated fadeIn">
  	<Row>
  		<Col :sm="24" :md="24" :lg="12">
  			<h3>11</h3>
  			<p>22</p>
  		</Col>
  	</Row>
  	<Table :columns="columns1" :data="data1"></Table>
  </div>
</template>
<script>
	export default {
	       data () {
	           return {
	              columns1: [
	                   {
	                       title: '姓名',
	                       key: 'name'
	                   },
	                   {
	                       title: '年龄',
	                       key: 'age'
	                   },
	                   {
	                       title: '地址',
	                       key: 'address'
	                   },
	                   {
                           title: '操作',
                           key: 'action',
                           width: 150,
                           align: 'center',
                           render: (h, params) => {
                               return h('div', [
                                   h('Button', {
                                       props: {
                                           type: 'primary',
                                           size: 'small'
                                       },
                                       style: {
                                           marginRight: '5px'
                                       },
                                       on: {
                                           click: () => {
                                               this.show(params.index)
                                           }
                                       }
                                   }, '查看'),
                                   h('Button', {
                                       props: {
                                           type: 'error',
                                           size: 'small'
                                       },
                                       on: {
                                           click: () => {
                                               this.remove(params.index)
                                           }
                                       }
                                   }, '删除')
                               ]);
                           }
                       }

	               ],
	               data1: [
	                   {
	                       name: '王小明',
	                       age: 18,
	                       address: '北京市朝阳区芍药居'
	                   },
	                   {
	                       name: '张小刚',
	                       age: 25,
	                       address: '北京市海淀区西二旗'
	                   },
	                   {
	                       name: '李小红',
	                       age: 30,
	                       address: '上海市浦东新区世纪大道'
	                   },
	                   {
	                       name: '周小伟',
	                       age: 26,
	                       address: '深圳市南山区深南大道'
	                   }
	               ]
	           }
	       },
	     }
</script>