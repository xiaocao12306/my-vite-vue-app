<template>
  <div class="upload">
      <label for="">
        <p>输入传送地址（完整的）先输入地址再放图片发的get请求</p>
        <a-input v-model:value="url" @change="onchange" style="width:300px;height:40px"/>
      </label>
      <a-upload-dragger
          v-model:fileList="fileList"
          name="file"
          :multiple="true"
          method='get'
          :action="url"
          @change="handleChange"
        >
          <p class="ant-upload-drag-icon">
            <inbox-outlined></inbox-outlined>
          </p>
          <p class="ant-upload-text">点击或者拖拽上传！</p>
          <p class="ant-upload-hint">
            点击上传图片或者拖拽上传
          </p>
      </a-upload-dragger>
  </div>
</template>

<script>

import { defineComponent, defineProps, reactive } from 'vue'
import { message } from 'ant-design-vue'

export default defineComponent({
  name:'HelloWorld',
  data(){
    return {
      url:''
    }
  },
  methods: {
    handleChange(){
      if (this.url == ''){
        message.info('你先输入地址！')
        return false
      }else{
        
      }
    }
  }
})
</script>

<style scoped>
a {
  color: #42b983;
}
.upload{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 400px;
  margin: 0 auto;
}
</style>
