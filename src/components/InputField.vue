<template>
    <div>
        <label for="">Name</label>
        <input 
            type="text" 
            :value="value" 
            style="padding: 30px; border: 2px solid green;"
            @input="$emit('input', $event.target.value)" 
            ><br/>

            <!-- 
                방법 1
                <input 
                    type="text" 
                    :value="value" 
                    style="padding: 30px; border: 2px solid green;"
                    @input="updateName" 
                    ><br/>
             -->

            <!-- 
                방법 2
                @input="updateName"가 아닌 아래처럼 input에 바로 넣는 방법도 있다. 
                @input="$emit('update-name', $event)" 
                emit을 사용하려면 아래에 선언된 updateName(e)도 주석처리 해줘야 한다. 

                <input 
                    type="text" 
                    :value="value" 
                    style="padding: 30px; border: 2px solid green;"
                    @input="$emit('update-name', $event)" 
                    ><br/>
            -->

            <!-- 
                방법 3
                HomeView.vue내 v-model로 설정한 name은 자식 뷰인 InputField.vue에 value로 들어온다.
                그래서 $event.target.value를 해줘야 한다. 
             -->


    </div>
</template>

<script>
export default {
    // 방법 1,2
    // props: {
    //     name: {
    //         type: String,
    //         required: true
    //     }
    // },

    // 방법 3
        props: {
            value: {
                type: String,
                required: true
            }   
    },
    // methods: {
    //     updateName(e) {
    //         console.log(e.target.value);
    //         this.$emit('update-name', e.target.value);
    //     }
    // }
}
</script>