<template>
    <div class="bb">
        <div class="all">aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</div>
        <div class="fix">fffffff</div>
    </div>
</template>
<script>
export default {
    data() {
        return {

        };
    },
};
</script>


<style lang="less">
.bb {
    margin-top: 100px;
    border: 1px solid red;
    position: relative;
    height: 40px;
    .all {
        position: absolute;
        left: 0;
        z-index: 1;
        background: #ccc;
    }
    .fix {
        position: absolute;
        left: 0;
        z-index: 1;
        background: red;
        color: #fff;
    }
}
</style>