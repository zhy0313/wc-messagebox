<template>
    <div v-show="show">
        <div class="popup popup-in" style="display: block;">
            <div class="popup-inner" :style="contentStyle">
                <div class="popup-title" v-if="title">{{title}}</div>
                <div class="popup-text">{{content}}</div>
            </div>
            <div class="popup-buttons">
                <span class="popup-button" :style="yes.style" @click="success">{{yes.text}}</span>
                <span class="popup-button" :style="no.style" @click="cancel">{{no.text}}</span>
            </div>
        </div>
        <div class="popup-backdrop active" style="display: block;"></div>
    </div>
</template>
<script>
    import pageChange from '../../mixins'
    export default {
        mixins: [pageChange],
        data () {
            return {
                show: true,
                title: '',
                content: '',
                contentStyle: {},
                yes: {
                    text: '确定',
                    style: {}
                },
                no: {
                    text: '取消',
                    style: {}
                }
            }
        },
        methods: {
            success () {
                this.show = false;
            },
            cancel () {
                this.show = false;
            }
        }
    }
</script>