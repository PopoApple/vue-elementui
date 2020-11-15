<template>
<div>
    <div class="color">
        xxx
    </div>
    <div :style="{background: $styleVars.colorSuccess}">
        fff
    </div>
</div>
</template>

<script>
export default {
 
}
</script>

<style lang="scss" scoped>

.color {
    color: $color-danger;
    border: 1px solid $color-success;
    background: $color-warning;
}
</style>