<template>
  <div class="form-group">
 
  <input 
      class="form-control"
      :class="{
        'is-invalid': isInvalid
        }"
      type="text"
      :value="value"
      @input="sendData($event)"
   />

  </div>  
</template>

<script>
export default {
    props:{
    value:{
        type: String,
        requried: true,
    }
    },
    computed: {
    isInvalid () {
      return  /[^a-z]/i.test(this.value)
        
    },
    },
    methods:{
        sendData ($event) {
            this.$emit('input', $event.target.value)
        }
    }
}
</script>