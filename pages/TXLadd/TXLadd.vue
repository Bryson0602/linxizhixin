<template>
    <view class="page-main">
        <cxy-cxy :dataList="dataList" @click="click"></cxy-cxy>
    </view>
</template>

 <!-- "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/3526efd7-7849-4764-8e53-256f929f9d65.jpeg",
        "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/4f9fe781-8823-4e3c-82e8-1c399c2d3cc2.jpeg",
        "",
        "",
        "",
        "",1234567890
        "",
        "",
        "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/50f52526-d071-4f38-bfc4-3857b69f40bb.jpeg" -->
<script>
    export default {
        data() {
            return {
                dataList: [{
                			status:'1',
                            id: '1',
                            name: '程碗饭',
                            phone: '灵犀号：8192759403',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/dffba366-8da1-4c25-8999-3dbf8322f33a.jpg'
                        }, {
                			status:'1',
                            id: '2',
                            name: '林淮',
                            phone: '灵犀号：5874029316',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/effc13a7-ad7b-4b94-a688-dea540ef8b5c.jpg'
                        }, {
                			status:'1',
                            id: '3',
                            name: 'Smile',
                            phone: '灵犀号：1234567890',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/5b260e5a-deda-434f-9d2d-53fc11d56635.jpg'
                        }, {
                			status:'1',
                            id: '4',
                            name: '好心情',
                            phone: '灵犀号：9876543210',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/0d465da8-02d8-4e04-b9f1-bf1397a06a8b.jpeg'
                        }, {
                			status:'1',
                            id: '5',
                            name: '橙子汽水',
                            phone: '灵犀号：2468135790',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/1ca5624c-fb5e-4483-8dd2-3f12eb5b5e1c.jpeg'
                        }, {
                			status:'1',
                            id: '6',
                            name: '日月星辰',
                            phone: '灵犀号：1357924680',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/07a69c17-695d-48da-ac83-d1dd4571aadc.jpeg'
                        }, {
                			status:'1',
                            id: '7',
                            name: '笑脸',
                            phone: '灵犀号：8642097531',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/cc23c896-3929-4217-b9e8-c1a439a454d0.jpeg'
                        }, {
                			status:'1',
                            id: '8',
                            name: '若楠',
                            phone: '灵犀号：1029384756',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/407a603d-1cf0-4a59-95b2-6353f5abf945.jpeg'
                        }, {
                			status:'1',
                            id: '9',
                            name: '冰川没有冰',
                            phone: '灵犀号：5192837460',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/abc5f4a6-9bb8-4dca-a7fb-07a64232b3b5.jpeg'
                        }, {
                			status:'1',
                            id: '10',
                            name: '听海风吹',
                            phone: '灵犀号：7354618290',
                            img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/be288d9d-9ebf-4ad1-9f03-8add77f5193e.jpeg'
                        },
                		{
                			status:'1',
                		    id: '11',
                		    name: '拥抱蓝天',
                		    phone: '灵犀号：2938475601',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/3526efd7-7849-4764-8e53-256f929f9d65.jpeg'
                		},
                		{
                			status:'1',
                		    id: '12',
                		    name: '新朋友',
                		    phone: '灵犀号：5061728394',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/4f9fe781-8823-4e3c-82e8-1c399c2d3cc2.jpeg'
                		},
                		{
                			status:'1',
                		    id: '13',
                		    name: '小雨',
                		    phone: '灵犀号：9182736450',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/c03f951d-b974-4814-8740-c2e9296c06b2.jpeg'
                		},
                		{
                			status:'1',
                		    id: '14',
                		    name: '好爱笑',
                		    phone: '灵犀号：7283940516',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/28b6e378-3195-49c2-9f97-3873f4c8ee00.jpeg'
                		},
                		{
                			status:'1',
                		    id: '15',
                		    name: '小晨',
                		    phone: '灵犀号：3546789201',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/50f52526-d071-4f38-bfc4-3857b69f40bb.jpeg'
                		},
                		{
                			status:'1',
                		    id: '16',
                		    name: '圆圆',
                		    phone: '灵犀号：4321098765',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/0a3b1ca1-017d-4da6-8ade-5e4143eb0569.jpeg'
                		},
                		{
                			status:'1',
                		    id: '17',
                		    name: '小曲奇',
                		    phone: '灵犀号：8765432109',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/9dfb88e2-b8ab-43db-b8b8-52049cc341a3.jpeg'
                		},
                		{
                			status:'1',
                		    id: '18',
                		    name: '快乐小猫',
                		    phone: '灵犀号：9203847561',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/74369003-da7d-4ab4-9bf1-a0054b0a4932.jpeg'
                		},
                		{
                			status:'1',
                		    id: '19',
                		    name: '梦想家',
                		    phone: '灵犀号：6152839470',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/eb06f8dc-3a44-4185-b718-cc840c650cc7.jpeg'
                		},
                		{
                			status:'1',
                		    id: '20',
                		    name: '自由飞翔',
                		    phone: '灵犀号：7890123456',
                		    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/77476b10-b696-4578-a10e-3cc419e07ae1.jpeg'
                		},
						{
							status:'1',
						    id: '21',
						    name: '小灵',
						    phone: '灵犀号：2387063291',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/503edc9b-c5d0-4661-8e82-5c728213e6b3.png'
						},
						{
							status:'1',
						    id: '213',
						    name: '涂涂',
						    phone: '灵犀号：6890421458',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/60fca11a-e373-437a-991b-c222b756404b.jpg'
						},
						{
							status:'1',
						    id: '214',
						    name: '胖虎',
						    phone: '灵犀号：4890321267',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/80d44e27-076a-43ad-b556-1e81793d52f3.jpg'
						},
						{
							status:'1',
						    id: '214',
						    name: '禾一',
						    phone: '灵犀号：8790321263',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/b49b553f-4f08-46dc-bc98-91d67c539710.jpg'
						},
						
						{
							status:'1',
						    id: '214',
						    name: 'i禾一',
						    phone: '灵犀号：3890071265',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/a6b205eb-2c4f-4ad4-93ba-074460367ab5.jpg'
						},
						{
							status:'1',
						    id: '214',
						    name: 'Sunshine',
						    phone: '灵犀号：0000000000',
						    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/beb51492-d52e-4919-a1ea-2a859c36a96a.jpg'
						},
						
						// 
						//         
						//         "",
						//         "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/b49b553f-4f08-46dc-bc98-91d67c539710.jpg",
						//         ""
                		]
                    }
                },
        methods: {
            //点击列表回调事件
            click(e) {
                console.log('点击列表回调：', e)
            }
        }
    }
	
</script>