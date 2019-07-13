<template>
    <div>
        <p><span>attr1: </span>{{divWidth}}</p>
        <p><span>attr2: </span>{{divHeight}}</p>
        <div width="123" height="123" style="border: 1px solid #000"></div>
    </div>
</template>

<script>
export default {
    name: 'TestComp',
    props: {
        attr1: Number,
        attr2: Number
    },
}
</script>

<style scoped>

</style>
