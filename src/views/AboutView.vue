<template>
  <div class="about">
    <h1>This is an about page</h1>
    <Zzee22su>
       This is slot area
       <!-- 
         v-slot:header은 ->  #header로 줄여서 쓸 수 있다.  
        
        방법 1
        <template #header="props">
          <p>slot name is header {{ props.kossie }}</p>
        </template> 

        방법 1을 방법 2처럼 사용할 수 있다. 


        방법 2
        <template #header="{ kossie }">
          <p>slot name is header {{ kossie }}</p>
        </template>
       -->
      <template #header="{ kossie }">
        <p>slot name is header {{ kossie }}</p>
      </template>
      <template v-slot:default>
        slot name is default 
      </template>
    </Zzee22su>
  </div>
</template>

<script>
import Zzee22su from '@/components/Zzee22su.vue'

export default {
  components: {
    Zzee22su
  }
}

</script>
