<template>
    <div id="Threshold">
        <chrange class="spacing" title="Hue" Xkey="hue" :maximum="180"></chrange>
        <chrange class="spacing" title="Saturation" Xkey="saturation" :maximum="255"></chrange>
        <chrange class="spacing" title="Value" Xkey="value" :maximum="255"></chrange>
        <chswitch class="spacing" title="Erode" Xkey="erode"></chswitch>
        <chswitch class="spacing" title="Dilate" Xkey="dilate"></chswitch>
    </div>
</template>
    
<script> 
import chrange from './ch-range.vue'
import chselect from './ch-select.vue'
import chswitch from './ch-switch.vue'
    export default {
        name: 'Threshold',
        data () {
            return {
            }
        },
        components:{
            chrange,
            chselect,
            chswitch
        },
        methods:{
        }
    }

</script>

<style scoped>
.spacing{
    margin-top: 20px;
}
</style>