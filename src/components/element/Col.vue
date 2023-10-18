<template>
    <div 
        :class="['el-col', classList]"
        :style="style">
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: 'ElCol',
    props: {
        span: {
            type: Number,
            default: 24
        },
        // 偏移量
        offset: {
            type: Number,
            default: 0
        },
        // 栅格向右移动格数
        push: {
            type: Number,
            default: 0
        },
        // 栅格向左移动格数
        pull: {
            type: Number,
            default: 0
        },
        xs: [Number, Object],
        sm: [Number, Object],
        md: [Number, Object],
        lg: [Number, Object],
        xl: [Number, Object]
    },
    computed: {
        gutter() {
            let parent = this.$parent;
            while(parent && parent.$options.name !== 'ElRow') {
                parent = parent.$parent;
            }

            return parent ? parent.gutter : 0
        },
        style() {
            const style = {};
            if (this.gutter) {
                style.paddingLeft = this.gutter / 2 + 'px';
                style.paddingRight = style.paddingLeft;
            }
            return style;
        },
        classList() {
            const classList = [];
            ['span', 'offset', 'push', 'pull'].forEach((prop) => {
                if (this[prop]) {
                    classList.push(
                        prop === 'span'
                        ? `el-col-${this[prop]}`
                        : `el-col-${prop}-${this[prop]}`
                    );
                }
            });

            ['xs', 'sm', 'md', 'lg', 'xl'].forEach((size) => {
                if (typeof this[size] === 'number') {
                    classList.push(`el-col-${size}-${this[size]}`);
                } else if (typeof this[size] === 'object') {
                    // {span, offset, push, pull}
                    const props = this[size];

                    Object.keys(props).forEach((prop) => {
                        classList.push(
                            prop == 'span'
                            ? `el-col-${size}-${props[prop]}`
                            : `el-col-${size}-${prop}-${props[prop]}`
                        )
                    })
                }
            });
    
            return classList;
        }
    },
}
</script>

<style lang="scss">
.el-col {
    float: left;
    box-sizing: border-box;
}

@for $i from 0 through 24 {
    .el-col-#{$i} {
        width: calc($i / 24) * 100%;
    }
    .el-col-offset-#{$i} {
        margin-left: calc($i / 24) * 100%;
    }
    .el-col-push-#{$i} {
        position: relative;
        left: calc($i / 24) * 100%;
    }
    .el-col-pull-#{$i} {
        position: relative;
        right: calc($i / 24) * 100%;
    }

    .el-col-sm-#{$i} {

    }
    // md lg xl
}

// xs < 768px
@media only screen and (max-width: 768px - 1) {
    @for $i from 0 through 24 {
        .el-col-xs-0 {
            display: none;
        }

        .el-col-xs-#{$i} {
            width: calc($i / 24) * 100%;
        }
        .el-col-xs-offset-#{$i} {
            margin-left: calc($i / 24) * 100%;
        }
        .el-col-xs-push-#{$i} {
            position: relative;
            left: calc($i / 24) * 100%;
        }
        .el-col-xs-pull-#{$i} {
            position: relative;
            right: calc($i / 24) * 100%;
        }

    }
    
}

// sm >= 768px
@media only screen and (min-width: 768px) {
    @for $i from 0 through 24 {
        .el-col-sm-0 {
            display: none;
        }

        .el-col-sm-#{$i} {
            width: calc($i / 24) * 100%;
        }
        .el-col-sm-offset-#{$i} {
            margin-left: calc($i / 24) * 100%;
        }
        .el-col-sm-push-#{$i} {
            position: relative;
            left: calc($i / 24) * 100%;
        }
        .el-col-sm-pull-#{$i} {
            position: relative;
            right: calc($i / 24) * 100%;
        }

    }
    
}

// md >= 992px
@media only screen and (min-width: 992px) {
    
    @for $i from 0 through 24 {
        .el-col-md-0 {
            display: none;
        }

        .el-col-md-#{$i} {
            width: calc($i / 24) * 100%;
        }
        .el-col-md-offset-#{$i} {
            margin-left: calc($i / 24) * 100%;
        }
        .el-col-md-push-#{$i} {
            position: relative;
            left: calc($i / 24) * 100%;
        }
        .el-col-md-pull-#{$i} {
            position: relative;
            right: calc($i / 24) * 100%;
        }

    }
}

// lg >= 1200px
@media only screen and (min-width: 1200px) {
    
    @for $i from 0 through 24 {
        .el-col-lg-0 {
            display: none;
        }

        .el-col-lg-#{$i} {
            width: calc($i / 24) * 100%;
        }
        .el-col-lg-offset-#{$i} {
            margin-left: calc($i / 24) * 100%;
        }
        .el-col-lg-push-#{$i} {
            position: relative;
            left: calc($i / 24) * 100%;
        }
        .el-col-lg-pull-#{$i} {
            position: relative;
            right: calc($i / 24) * 100%;
        }

    }
}

// xl >= 1920px
@media only screen and (min-width: 1920px) {
    
    @for $i from 0 through 24 {
        .el-col-xl-0 {
            display: none;
        }

        .el-col-xl-#{$i} {
            width: calc($i / 24) * 100%;
        }
        .el-col-xl-offset-#{$i} {
            margin-left: calc($i / 24) * 100%;
        }
        .el-col-xl-push-#{$i} {
            position: relative;
            left: calc($i / 24) * 100%;
        }
        .el-col-xl-pull-#{$i} {
            position: relative;
            right: calc($i / 24) * 100%;
        }

    }
}
</style>