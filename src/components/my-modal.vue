<template>
  <div >
       <Modal
        v-model="the_show"
        title="Common Modal dialog box title"
        @on-ok="ok"
        @on-cancel="cancel">
        <p>Content of dialog</p>
    </Modal>
  </div>
</template>

<script>
export default {
    name:'myModal',
    model:{
        prop: 'show',            
        event: 'changed'       
    },
    data() {
        return {
            the_show:this.show
        }
    },
    watch:{
        show(newVal) {
            this.the_show = newVal
        }
    },
    props:{
        show:{
            type:Boolean,
            default:() => false
        },
        msg:{
            type:String,
            default:() => 'yuluwugua'
        }
    },
    methods:{
       ok() {
            this.$emit('changed',false)
            console.log('this.msg',this.msg)
            this.$emit('get-msg',this.msg)
            this.$emit('on-ok')
       },
        cancel() {
            this.$emit('changed',false)
            this.$emit('on-close')

        }
    }
}
</script>

<style>

</style>