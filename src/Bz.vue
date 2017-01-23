<template>
  <textarea @focusin="focusin" @focusout="focusout" @input="input" v-model="value_bz"></textarea>
</template>

<script>
  export default {
    watch: {
      'value_bz': function (val) {
        this.$emit('input', val)
      }
    },
    props: {
      value: {
        type: String,
        default: ''
      }
    },
    components: {
    },
    mounted: function () {
      this.value_bz = this.value
      this.$nextTick(function () {
        this.$el.setAttribute('style', 'height:' + (this.$el.scrollHeight) + 'px;overflow-y:hidden;')
      })
    },
    data: function () {
      return {
        value_bz: ''
      }
    },
    methods: {
      input: function () {
        this.$el.style.height = 'auto'
        this.$el.style.height = (this.$el.scrollHeight) + 'px'
      },
      focusin: function (e) {
        this.$emit('focusin', e)
      },
      focusout: function (e) {
        this.$emit('focusout', e)
      }
    }
  }
</script>
