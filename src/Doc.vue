<template>
  <div>
    <doc :name="name"
      :desc="desc"
      :parm_desc="parm_desc"
      :parms="parms"
      :code="code"
      >
      <bz v-model="data"></bz>
    </doc>
  </div>
</template>
<script>
  // import toastr from 'toastr'

  import Bz from './Bz'
  import Doc from 'bz-doc'
  export default {
    components: {
      Bz,
      Doc
    },
    data: function () {
      return {
        data: '测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试',
        loading: false,
        name: 'bz-auto-height-textarea',
        desc: '自动高度的textarea',
        parms: [
          {parm: 'v-model', desc: '和正常的textarea一样的用'}
        ],
        parm_desc: ``,
        code: `<bz v-model="data"></bz>`
      }
    },
    methods: {
      call_back: function (user_name, password) {
        this.loading = true
        let _this = this
        window.setTimeout(function () {
          window.alert(`user_name:${user_name}, password: ${password}`)
          // toastr.info('登录成功')
          _this.loading = false
        }, 2000)
      }
    }
  }
</script>
