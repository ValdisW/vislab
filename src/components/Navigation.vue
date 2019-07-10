<template>
    <div>
        <div class="container">
            <ul>
                <li><a :href="homelink">Home</a></li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Navigation',
    props: {
        homelink: String
    }
}
</script>

<style scoped>
    
    ul{
        height: 60px; width: 100%;
        background-color: #aaa;
        box-shadow: 0 0 10px 0 #aaa;
    }
    ul>li{
        float: right;
        list-style: none;
        height: 40px; width: 100px;
        line-height: 40px;
        text-align: center;
        margin-top: 10px;
        margin-right: 20px;
        transition: 0.15s;
    }
    ul>li:hover{
        background-color: #222;
    }
    ul>li>a{
        color: #fff;
        text-decoration: none;
    }
</style>
