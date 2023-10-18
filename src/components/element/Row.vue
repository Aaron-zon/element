<template>
    <div
        :class="[
            'el-row',
            {'el-row--flex': this.type === 'flex'},
            this.justify !== 'start' && `is-jusitify-${justify}`,
            this.align !== 'top' && `is-align-${justify}`,
        ]" 
        class="el-row el-row--flex" :style="style">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'ElRow',
    props: {
        // 间隔
        gutter: {
            type: Number,
            default: 0
        },
        // display
        type: String,
        // 水平对其方式
        justify: {
            type: String,
            default: 'start',
            validator: val => [ 'start', 'end', 'center', 'space-between', 'space-around'].includes(val)
        },
        align: {
            type: String,
            default: 'top',
            validator: val => [ 'top', 'middlw', 'bottom'].includes(val)
        }
    },
    computed: {
        style() {
            const style = {};
            if (this.gutter) {
                style.marginLeft = -this.gutter / 2 + 'px';
                style.marginRight = style.marginLeft;
            }
            return style;
        },
    }
}
</script>

<style lang="scss">
.el-row {
    &::after,
    &::before {
        display: block;
        content: '';
    }
    &::after {
        clear: both;
    }

    &--flex {
        display: flex;

        &::after,
        &::before {
            display: none;
        }

        &.is-jusitify-end {
            justify-content : flex-end;
        }

        &.is-jusitify-center {
            justify-content : center;
        }

        &.is-jusitify-space-between {
            justify-content : space-between;
        }

        &.is-jusitify-space-around {
            justify-content : space-around;
        }

        &.is-align-middlw {
            align-items: center;
        }

        &.is-align-bottom {
            align-items: flex-end;
        }
    }
}


</style>