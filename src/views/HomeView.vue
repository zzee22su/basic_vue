<template>
  <div>
    <h1>
      This is Home page
    </h1>
    <form action="">
      <InputField :name="name" @update-name="updateName"/>
      <button>Submit</button>
    </form>
    {{ name }}
    <!-- 
      방법 2
      InputField.vue에서 보낸 $event를
      @update-name="name = $event.target.value"로 받을 수 있다. 
      아래에 선언된 method updateName(name)은 주석처리 해야 한다. 
     -->
  </div>
</template>

<script>
import InputField from '@/components/InputField.vue'

export default {
  components: {
    InputField
  },

  data() {
    return {
      name: ''
    }
  },

  methods: {
    updateName(name) {
      this.name = name;
    }
  }

}
</script>

<style scoped>
/* 
scoped : 해당 template style이 적용될 수 있도록 하는 속성,
scoped를 설정해주지 않으면 어플리케이션 전체에 적용이 된다.  
*/
h1 {
  color : rgb(138, 195, 248);
}
</style>