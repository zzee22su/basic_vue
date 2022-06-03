<template>
  <div>
    <h1>
      This is Home page
    </h1>
    <form action="">
      <InputField v-model="name"/>
      <button>Submit</button>
    </form>
    {{ name }}

    <!-- 
      방법 1
      <InputField :name="name" @update-name="updateName"/>
      
      자식이(InputField) 보낸 값을 부모가(HomeView) 받기 위해서 
      자식 뷰내에 updateName(e)에서 emit name으로 설정한 'update-name'을 
      이벤트 이름으로 설정한다 -> @update-name 그리고 아래 method에 updateName도 설정해준다.
     -->

    <!-- 
      방법 2
      InputField.vue에서 보낸 $event를
      @update-name="name = $event.target.value"로 받을 수 있다. 
      아래에 선언된 method updateName(name)은 주석처리 해야 한다. 

      <InputField :name="name" @update-name="name = $event.target.value"/>
     -->

     <!-- 
       방법 3
       컴포넌트에도 v-model을 사용할 수 있다. 
       InputFiled에 v-model을 넣어주면 자동으로 자식 컴포넌트에 value로 보내게 된다. 
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