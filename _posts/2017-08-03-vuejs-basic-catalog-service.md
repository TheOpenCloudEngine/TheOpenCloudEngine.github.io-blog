---
layout: post
title:  "Vue JS 를 이용한 쇼핑몰 사이트"
date:   2017-08-03
writer:  장진영
author:  장진영
categories: [vue-js]
---

# Level 1:  vue js 와 vue-material 을 이용한 
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hello Vue</title>
</head>



<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-material@0.7.1"></script>
<link rel="stylesheet" href="https://unpkg.com/vue-material@0.7.1/dist/vue-material.css">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

<script>

    Vue.use(VueMaterial)

</script>


<body>

<div id="page">


    <md-card>
        <md-card-media>
            <img src="http://gdimg.gmarket.co.kr/994016238/still/160" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품</div>
            <div class="md-subhead">22,000</div>
        </md-card-header>

        <md-card-actions>
            <md-button>장바구니</md-button>
            <md-button>바로구매</md-button>
        </md-card-actions>

        <md-card-content>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
        </md-card-content>
    </md-card>

    <md-card>
        <md-card-media>
            <img src="http://gdimg.gmarket.co.kr/880598217/still/160" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">스윙바로/개인용스크린골프/어프로치/퍼팅/장타/게임</div>
            <div class="md-subhead">345,000</div>
        </md-card-header>

        <md-card-actions>
            <md-button>장바구니</md-button>
            <md-button>바로구매</md-button>
        </md-card-actions>

        <md-card-content>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
        </md-card-content>
    </md-card>

    <md-card>
        <md-card-media>
            <img src="http://gdimg.gmarket.co.kr/728059781/still/160" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">Title goes here</div>
            <div class="md-subhead">Subtitle here</div>
        </md-card-header>

        <md-card-actions>
            <md-button>Action</md-button>
            <md-button>Action</md-button>
        </md-card-actions>

        <md-card-content>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
        </md-card-content>
    </md-card>

</div>


</body>


<script>

    new Vue({el:'#page'});

</script>
</html>
```


# Level 2:  component 화
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Hello Vue</title>
</head>


<script src="https://unpkg.com/vue"></script>

<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-material@0.7.1"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.3.3/require.js"></script>
<link rel="stylesheet" href="https://unpkg.com/vue-material@0.7.1/dist/vue-material.css">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">


<script type="text/x-template" id="catalog-item-template">

    <md-card>
        <md-card-media>
            <img :src="imgUrl" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">{{title}}</div>
            <div class="md-subhead">{{price}} 원</div>
        </md-card-header>

        <md-card-actions>
            <md-button>장바구니</md-button>
            <md-button>바로구매</md-button>
        </md-card-actions>

        <md-card-content>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
        </md-card-content>
    </md-card>

</script>

<script>


    Vue.use(VueMaterial)


    Vue.component('catalog-item', {
        template: "#catalog-item-template",
        props: {
            imgUrl: String,
            title: String,
            price: Number,
        },
    });
</script>


<body>

<div id="page">


    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>
    <catalog-item img-url="http://gdimg.gmarket.co.kr/994016238/still/160" title="골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품" price="25000"></catalog-item>

</div>


</body>


<script>

    new Vue({
        el:'#page'
    });

</script>
</html>
```

# Level 3: 검색과 필터링
```
<html>
    <meta charset="UTF-8">
    <title>나만의 쇼핑몰</title>


<script src="https://unpkg.com/vue"></script>

<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-material@0.7.1"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.3.3/require.js"></script>
<link rel="stylesheet" href="https://unpkg.com/vue-material@0.7.1/dist/vue-material.css">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">



<script type="text/x-template" id="catalog-item-template">

    <md-card>

        <md-card-media>
            <img :src="imgUrl" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">{{title}}</div>
            <div class="md-subhead">{{price}} 원</div>
        </md-card-header>

        <md-card-actions>
            <md-button>장바구니</md-button>
            <md-button>바로구매</md-button>
        </md-card-actions>

        <md-card-content>
            {{description}}
        </md-card-content>
    </md-card>

</script>

<script>


    Vue.use(VueMaterial)


    Vue.component('catalog-item', {
        template: "#catalog-item-template",
        props: {
            imgUrl: String,
            title: String,
            price: Number,
            description: String
        },
    });
</script>


<body>

<div id="page">
    <form novalidate @submit.stop.prevent="submit">
        <md-input-container>
            <label>검색</label>
            <md-input v-model="searchQuery"></md-input>
        </md-input-container>
    </form>

    <md-layout md-gutter>
        <md-layout  v-for="item in filteredItems" md-flex-xsmall="100" md-flex-small="50" md-flex-medium="33">
            <catalog-item :img-url="item.imgUrl" :title="item.title" :price="item.price" :description="item.description"></catalog-item>
        </md-layout>
    </md-layout>


</div>


</body>


<script>

    new Vue({
        el:'#page',

        data: {

            catalogItems:[
                {imgUrl:'http://gdimg.gmarket.co.kr/994016238/still/160', price: 25000, title: '골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품', description:''},
                {imgUrl:'http://gdimg.gmarket.co.kr/728059781/still/160', price: 25000, title: '스윙바로/개인용스크린골프/어프로치/퍼팅/장타/게임', description:''},
                {imgUrl:'http://gdimg.gmarket.co.kr/994016238/still/160', price: 25000, title: '골프 랑 올양피 골프장갑(왼손) 남성용 4장 골프용품', description:''},
            ],

            searchQuery: ''


        },

        computed: {
            filteredItems: function () {
                var filterKey = this.searchQuery && this.searchQuery.toLowerCase()
                var data = this.catalogItems
                if (filterKey) {
                    data = data.filter(function (row) {
                        return Object.keys(row).some(function (key) {
                            return String(row[key]).toLowerCase().indexOf(filterKey.trim()) > -1
                        })
                    })
                }

                return data
            }
        },

    });

</script>
</html>
```

# Level 4: Couchbase의 사용

```
<html>
    <meta charset="UTF-8">
    <title>나만의 쇼핑몰</title>


<script src="https://unpkg.com/vue"></script>

<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-material@0.7.1"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.3.3/require.js"></script>
<link rel="stylesheet" href="https://unpkg.com/vue-material@0.7.1/dist/vue-material.css">
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">



<script type="text/x-template" id="catalog-item-template">

    <md-card>

        <md-card-media>
            <img :src="imgUrl" alt="People">
        </md-card-media>

        <md-card-header>
            <div class="md-title">{{title}}</div>
            <div class="md-subhead">{{price}} 원</div>
        </md-card-header>

        <md-card-actions>
            <md-button>장바구니</md-button>
            <md-button>바로구매</md-button>
        </md-card-actions>

        <md-card-content>
            {{description}}
        </md-card-content>
    </md-card>

</script>

<script>


    Vue.use(VueMaterial)


    Vue.component('catalog-item', {
        template: "#catalog-item-template",
        props: {
            imgUrl: String,
            title: String,
            price: Number,
            description: String
        },

    });
</script>


<body>

<div id="page">
    <form novalidate @submit.stop.prevent="submit">
        <md-input-container>
            <label>검색</label>
            <md-input v-model="searchQuery"></md-input>
        </md-input-container>
    </form>

    <md-layout md-gutter>
        <md-layout  v-for="item in filteredItems" md-flex-xsmall="100" md-flex-small="50" md-flex-medium="33">
            <catalog-item :img-url="item.imgUrl" :title="item.title" :price="item.price" :description="item.description"></catalog-item>
        </md-layout>
    </md-layout>


</div>


</body>


<script>

    new Vue({
        el:'#page',

        data: function(){

            var catalogItems;
            var xhttp = new XMLHttpRequest();
            xhttp.onreadystatechange = function() {
                if (this.readyState == 4 && this.status == 200) {
                    catalogItems = JSON.parse(this.responseText);
                }else{
                    //오추출력
                }
            };
            xhttp.open("GET", "http://192.168.0.7:8091/pools/default/buckets/default/docs/", false);
            xhttp.send();

            catalogItems = catalogItems.rows;

            for(var idx in catalogItems){
                var item = catalogItems[idx];

                xhttp.onreadystatechange = function() {
                    if (this.readyState == 4 && this.status == 200) {
                        catalogItems[idx] = JSON.parse(this.responseText).json;
                    }
                };
                xhttp.open("GET", "http://192.168.0.7:8091/pools/default/buckets/default/docs/" + item.id, false);
                xhttp.send();

            }

            return {
                catalogItems: catalogItems
                ,
                searchQuery:''
            }

        },

        computed: {
            filteredItems: function () {
//                var filterKey = this.searchQuery && this.searchQuery.toLowerCase()
//                var data = this.catalogItems
//                if (filterKey) {
//                    data = data.filter(function (row) {
//                        return Object.keys(row).some(function (key) {
//                            return String(row[key]).toLowerCase().indexOf(filterKey.trim()) > -1
//                        })
//                    })
//                }
//
//                return data

                if (this.searchQuery) { // 검색어가 입력되면
                    var data = [];

                    for(var i in this.catalogItems){  // 각자의 카탈로그 아이템들에 대하여
                        var item = this.catalogItems[i];  // 각 카탁로그 아이템 하나

                        if(item.title.indexOf(this.searchQuery) > -1)  // 상품의 이름에 검색어가 어딘가 있다면
                            data.push(item);   // 필터링 대상에 현재 상품 추가
                    }

                    return data;
                }


                return this.catalogItems;

            }
        },

    });

</script>
</html>
```
