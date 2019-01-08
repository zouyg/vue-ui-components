<template>
    <div class="col" :class="colClass" :style="colStyle">
        <slot></slot>
    </div>
</template>

<script>
    let validator =  (value) => {
        let keys = Object.keys(value);
        let valid = true;
        keys.forEach(key=>{
            if(!['span', 'offset'].includes(key)){
                valid = false
            }
        });
        return valid;
    };
    export default {
        name: "GuluCol",
        props: {
            span: { type: [Number, String] },
            offset: { type: [Number, String] },
            pad: { type: Object, validator },
            narrowPc: { type: Object, validator},
            pc: { type: Object, validator },
            widePc: { type: Object, validator }
        },
        data(){
            return {
                gutter: 0
            }
        },
        methods:{
            createClasses (obj, str = '') {
                let arr = []
                if(!obj){ return [] }
                if(obj.span){ arr.push(`col-${str}${obj.span}`) }
                if(obj.offset){ arr.push(`col-${str}${obj.offset}`) }
                return arr;
            }
        },
        computed: {
            colClass(){
                let {span, offset, pad, narrowPc, pc, widePc} = this;
                return [
                    ...this.createClasses({span, offset}),
                    ...this.createClasses(pad, 'pad-'),
                    ...this.createClasses(narrowPc, 'narrow-pc-'),
                    ...this.createClasses(pc, 'pc-'),
                    ...this.createClasses(widePc, 'wide-pc-')
                ]
            },
            colStyle() {
                return {
                    paddingLeft: this.gutter / 2 + 'px',
                    paddingRight: this.gutter / 2 + 'px'
                }
            }
        }
    }
</script>


<style scoped lang="scss">
    .col {
        /*width: 50%;*/
        height: 100px;
        background: grey;
        border: 1px solid red;
        /*margin: 0 10px;*/

        @for $n from 1 through 100 {
            &.col-#{$n} {
                width: ($n / 24) * 100%;
            }
        }

        @for $n from 1 through 100 {
            &.offset-#{$n} {
                margin-left: ($n / 24) * 100%;
            }
        }

        @media (min-width: 576px) {
            @for $n from 1 through 100 {
                &.col-pad-#{$n} {
                    width: ($n / 24) * 100%;
                }
            }

            @for $n from 1 through 100 {
                &.offset-pad-#{$n} {
                    margin-left: ($n / 24) * 100%;
                }
            }
        }
        @media (min-width: 769px) {
            @for $n from 1 through 100 {
                &.col-narrow-pc-#{$n} {
                    width: ($n / 24) * 100%;
                }
            }

            @for $n from 1 through 100 {
                &.offset-narrow-pc-#{$n} {
                    margin-left: ($n / 24) * 100%;
                }
            }
        }
        @media (min-width: 993px) {
            @for $n from 1 through 100 {
                &.col-pc-#{$n} {
                    width: ($n / 24) * 100%;
                }
            }

            @for $n from 1 through 100 {
                &.offset-pc-#{$n} {
                    margin-left: ($n / 24) * 100%;
                }
            }
        }
        @media (min-width: 1201px) {
            @for $n from 1 through 24 {
                &.col-wide-pc-#{$n} {
                    width: ($n / 24) * 100%;
                }
            }
            @for $n from 1 through 24 {
                &.offset-wide-pc-#{$n} {
                    margin-left: ($n / 24) * 100%;
                }
            }
        }
    }
</style>