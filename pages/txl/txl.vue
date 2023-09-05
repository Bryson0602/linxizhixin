<template>
    <view class="page-main">
        <liu-indexed-list :dataList="dataList" @click="click"></liu-indexed-list>
    </view>
</template>

 <!-- "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/3526efd7-7849-4764-8e53-256f929f9d65.jpeg",
        "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/4f9fe781-8823-4e3c-82e8-1c399c2d3cc2.jpeg",
        "",
        "",
        "",
        "",
        "",
        "",
        "https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/50f52526-d071-4f38-bfc4-3857b69f40bb.jpeg" -->
<script>
    export default {
        data() {
            return {
                dataList: [{
                    id: '1',
                    name: '程碗饭',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/dffba366-8da1-4c25-8999-3dbf8322f33a.jpg'
                }, {
                    id: '2',
                    name: '林淮',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/effc13a7-ad7b-4b94-a688-dea540ef8b5c.jpg'
                }, {
                    id: '3',
                    name: 'Smile',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/5b260e5a-deda-434f-9d2d-53fc11d56635.jpg'
                }, {
                    id: '4',
                    name: '好心情',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/0d465da8-02d8-4e04-b9f1-bf1397a06a8b.jpeg'
                }, {
                    id: '5',
                    name: '橙子汽水',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/1ca5624c-fb5e-4483-8dd2-3f12eb5b5e1c.jpeg'
                }, {
                    id: '6',
                    name: '日月星辰',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/07a69c17-695d-48da-ac83-d1dd4571aadc.jpeg'
                }, {
                    id: '7',
                    name: '笑脸',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/cc23c896-3929-4217-b9e8-c1a439a454d0.jpeg'
                }, {
                    id: '8',
                    name: '若楠',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/407a603d-1cf0-4a59-95b2-6353f5abf945.jpeg'
                }, {
                    id: '9',
                    name: '冰川没有冰',
                    phone: '18198045576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/abc5f4a6-9bb8-4dca-a7fb-07a64232b3b5.jpeg'
                }, {
                    id: '10',
                    name: '听海风吹',
                    phone: '181****5576',
                    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/be288d9d-9ebf-4ad1-9f03-8add77f5193e.jpeg'
                },
				{
				    id: '11',
				    name: '拥抱蓝天',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/3526efd7-7849-4764-8e53-256f929f9d65.jpeg'
				},
				{
				    id: '12',
				    name: '新朋友',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/4f9fe781-8823-4e3c-82e8-1c399c2d3cc2.jpeg'
				},
				{
				    id: '13',
				    name: '小雨',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/c03f951d-b974-4814-8740-c2e9296c06b2.jpeg'
				},
				{
				    id: '14',
				    name: '好爱笑',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/28b6e378-3195-49c2-9f97-3873f4c8ee00.jpeg'
				},
				{
				    id: '15',
				    name: '小晨',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/50f52526-d071-4f38-bfc4-3857b69f40bb.jpeg'
				},
				{
				    id: '16',
				    name: '圆圆',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/0a3b1ca1-017d-4da6-8ade-5e4143eb0569.jpeg'
				},
				{
				    id: '17',
				    name: '小曲奇',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/9dfb88e2-b8ab-43db-b8b8-52049cc341a3.jpeg'
				},
				{
				    id: '18',
				    name: '快乐小猫',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/74369003-da7d-4ab4-9bf1-a0054b0a4932.jpeg'
				},
				{
				    id: '19',
				    name: '梦想家',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/eb06f8dc-3a44-4185-b718-cc840c650cc7.jpeg'
				},
				{
				    id: '20',
				    name: '自由飞翔',
				    phone: '181****5576',
				    img: 'https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/77476b10-b696-4578-a10e-3cc419e07ae1.jpeg'
				},
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