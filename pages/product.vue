<template>
    <div class="product-container">
        <section class="tabs">
            <a v-on:click="changeTab(product)" v-for="product in products" :key="product.id" :class="['tab',{active : currentTab == product.id}]">
                {{ product.tabname }}
            </a>
        </section>
        <div class="product" v-for="product in products" :key="product.id" v-show="currentTab == product.id" itemscope itemtype="http://schema.org/Product">
            <div class="background"></div>
            <section class="cat-tabs">
                <a v-on:click="changeTab(product)" class="cat-tab" v-for="(categorie, index) in categories" :key="categorie.name" :class="{'active': index === 0 }">
                    {{ categorie.name }}
                </a>
            </section>
            <div class="rows">
                <div class="row-left">
                    <div class="name-box">
                        <h2 itemprop="name">{{product.name}}</h2>
                    </div>
                    <div class="includes">
                        <h4>Software Includes:</h4>
                        <img class="thumbnail" src="~/assets/include-word.png" alt="Microsoft Word">
                        <img class="thumbnail" src="~/assets/include-excel.png" alt="Microsoft Excel">
                        <img class="thumbnail" src="~/assets/include-power.png" alt="Microsoft Power Point">
                    </div>  
                    <div class="price-box">
                        <div class="price" itemprop="offers" itemscope itemtype="http://schema.org/Offer">
                            <span class="currency" itemprop="priceCurrency" content="USD">$</span>
                            <span class="value" itemprop="price">258</span>
                            <span class="decimal">98</span>
                        </div>
                        <span class="old-price">$258.98</span>
                    </div>
                    <div class="button-shop">
                        <button>Shop Now</button>   
                    </div>
                </div>
                <div class="row-right">
                    <img class="image-product" src="../assets/product-image.png" alt= {{ product.name }} itemprop="image"/>
                </div>
            </div>
            <div class="product-description">
                <p itemprop="description">
                    Microsoft Office has been the standard for office software for decades. Its core programs, Word, Excel, and Pc businesses around the world. With over 1.2 billion users worldwide, Microsoft Office is the most popular office there's enhancements and new features to make it even better than before.
                    Microsoft Office has been the standard for office software for decades. Its core programs, Word, Excel, and Pc businesses around the world. With over 1.2 billion users worldwide,
                </p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        head() {
            return {
                title: 'Product Page',
                meta: [
                    {
                        hid: 'description',
                        name: 'description',
                        content: 'Front End Test'
                    }
                ]
            };
        },
        data: () => ({
            products: [
                { name: 'Microsoft Office 2019 Home & Student', tabname: 'Office 2019', id:1, },
                { name: 'Microsoft Office 2016 Home & Student', tabname: 'Office 2016', id:2, },
                { name: 'Microsoft Office 2013 Home & Student', tabname: 'Office 2013', id:3, },
                { name: 'Microsoft Office 2010 Home & Student', tabname: 'Office 2010', id:4, },
                { name: 'Microsoft Office 365 Home & Student', tabname: 'Office 365',  id:5, }
            ],
            categories: [
                {name: 'Standart'},
                {name: 'Home & Student'},
                {name: 'Home & Business'},
                {name: 'Professional'},
                {name: 'Professional Plus'},
            ],
            currentTab: 1,
            typeSelected: null
        }),
        methods: {
            changeTab(product) {
                this.currentTab = product.id;
            },
        },
    };
</script>

<style lang="less" scoped>

.product-container {
    position: relative;
    width: 60%;
    margin: 7% auto;
    font-family: Arial, Helvetica, sans-serif;
    .tabs {
        width: 100%;
        display: flex;
        align-items: flex-end;
        font-weight: 100;
        font-size: 18px;
        a {
            position: relative;
            width: 100%;
            padding: 5px 30px 20px;
            font-weight: 100;
            font-family: sans-serif;
            font-size: 25px;
            color: #6D8FA0;
            border-bottom: solid 2px #D3DDE4;
            cursor: pointer;
            &.active {
                width: 100%;
                display: block;
                font-size: 35px;
                color: #000;
                &::after {
                    content: '';
                    position: absolute;
                    top: 63px;
                    left: 0;
                    width: 20px;
                    height: 20px;
                    background: #0993E5;
                    z-index: 99;
                }
            }
            &:after {
                content: '';
                position: absolute;
                top: 50px;
                left: 0;
                width: 10px;
                height: 10px;
                background: #ccc;
                z-index: 99;
            }
        }
    }
    .product {
        flex-direction: row;
        font-size: 20px;
        font-weight: normal;
        color: #6C8E9F;
        font-family: Ubuntu, sans-serif;
        .background {
            position: absolute;
            padding: 210px 225px;
            display: table;
            background: #F2F5F7;
            z-index: -1;
        }
        .cat-tabs {
            width: 100%;
            padding: 40px 0 0 25px;
            display: flex;
            align-items: flex-end;
            font-weight: 100;
            font-size: 18px;
           .cat-tab {
                position: relative;
                width: 100%;
                font-weight: 100;
                font-family: sans-serif;
                font-size: 20px;
                color: #6D8FA0;
                cursor: pointer;
                &.active {
                    margin-left: 50px;
                    color: #0A92E4;
                    font-size: 27px;
                    font-weight: 400;
                    letter-spacing: 2px;
                }
           }
        }
        .rows {
            display: flex;
            .row-left {
                width: 45%;
                .name-box {
                    margin: 50px 0 0 110px;
                    display: inline-block;
                    font-size: 26px;
                    font-weight: 100;
                    letter-spacing: 3px;
                    color: #042338;
                    line-height: 55px;
                    h2 {
                        font-weight: 100;
                    }
                }
                .includes {
                    margin: 35px 0 0 110px;
                    h4 {
                        margin-bottom: 15px;
                        color: #000;
                        font-weight: 400;
                        font-size: 15px;
                    }
                    .thumbnail {
                        width: 35px;
                        height: 35px;
                        margin: 0 5px;
                        display: inline-block;
                        &:first-of-type {
                            margin-left: 0;
                        }
                    }
                }
                .price-box {
                    margin-top: 18px;
                    display: flex;
                    .price {
                        margin: 45px 0 0 110px;
                        letter-spacing: 0px;
                        font-weight: 400;
                        color: #042338;
                        .currency {
                            vertical-align: top;
                            font-size: 19px;
                            line-height: 0.8;
                        }
                        .value {
                            font-size: 53px;
                        }
                        .decimal {
                            vertical-align: top;
                            letter-spacing: 0;
                            font-size: 25px;
                            line-height: 0.8;
                        }
                    }
                    .old-price {
                        margin: 30px 0 0 35px;
                        font-size: 29px;
                        color: #6D8FA0;
                        font-weight: bold;
                        text-decoration: line-through;
                    }
                }
                .button-shop {
                    width: 65%;
                    margin-top: 30px;
                    text-align: center;
                    button {
                        padding: 18px 50px;
                        text-align: center;
                        text-transform: uppercase;
                        border: none;
                        color: #fff;
                        text-shadow: 0px 0px 10px rgba(0,0,0,0.2);
                        font-size: 13px;
                        font-weight: 600;
                        box-shadow: 0 0 20px #eee;
                        background-image: linear-gradient(to right, #F7701C 0%, #F78A18 51%, #F7A415 100%);
                        background-size: 200% auto;
                        transition: 0.5s;
                        cursor: pointer;
                        &:hover {
                            background-position: right center;
                        }
                    }
                }
            }
            .row-right {
                margin-top: 120px;
                .image-product {
                    width: 350px;
                }
            }
        }
        .product-description {
            width: 85%;
            margin-top: 120px;
            font-size: 15px;
            font-weight: 400;
            text-align: left;
            color: #6E90A1;
            line-height: 35px;
            p {
                margin: 0;
            }
        }
    }
}
</style>
