<template>
    <Row type="flex" justify="start" align="middle" :gutter="1" >
        <Col span="4">
            <h4>{{title.charAt(0).toUpperCase() + title.slice(1)}} :</h4>
        </Col>
        <Col span="4">
            <i-select v-model="value" size="small" @on-change="handleInput">
                <i-option v-for="(item,index) in list" :value="index" :key="index">{{item}}</i-option>
            </i-select>
        </Col>
    </Row>
</template>

<script>
    export default {
        name: 'ch-select',
        props:{
            title: String,
            list: Array,
            Xkey: String
        },
        data() {
            return {
            
            }
        },
        methods: {
            handleInput() {
                this.$socket.sendObj({[this.Xkey]:this.value});
            }
        },
        computed:{
            value:{
                get: function(){
                    return this.$store.state[this.Xkey];
                },
                set: function(value){
                    this.$store.commit(this.Xkey,value);
                }
            }
        }
    }
</script>

<style>
h4 {
     color: #e6ebf1;
      text-align: left;
 }
 /* .ivu-select-selection{
     background-color: #2c3e50 !important;
 } */
 /* .ivu-select-selected-value{
     color: #fff !important;
 } */

</style>