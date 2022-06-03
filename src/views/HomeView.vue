<template>
  <div>
    <h1>
      This is Home page
    </h1>
    <Zzee22su/>
  </div>
</template>

<script>
import Zzee22su from '@/components/Zzee22su.vue';

export default {
  components: {
    Zzee22su
  },

  data() {
    return {
      name: 'Zzee22su'
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