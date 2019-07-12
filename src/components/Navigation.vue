<template>
    <div id="navigation">
        <!-- <div class="container">
            <ul>
                <li><a :href="homelink">Home</a></li>
            </ul>
        </div> -->
        <v-toolbar dense>
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title>VisLab</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn flat>link1</v-btn>
                <v-btn flat>link2</v-btn>
                <v-btn flat>link3</v-btn>
            </v-toolbar-items>
        </v-toolbar>
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
    /* #navigation{
        position: fixed;
        top: 0; left: 0;
    }
    .container{
        float: right;
    }
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
    } */
</style>
