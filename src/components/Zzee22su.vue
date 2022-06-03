<template>
    <div>
        <h1>{{ title }}</h1>
        <!-- 다른 html 코드를 사용하고 싶을 때, slot을 사용한다. -->
        <p>{{ name }}</p>
        <button @click="updateName">Change Name</button>

        <p>Header</p>
        <slot name="header" :kossie="kossie"></slot>
        <p>Body</p>
        <slot></slot>
        <p>Footer</p>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            required: false,
            default: 'default title'
        },
        
        name: {
            type: String,
            default: 'default name'
        }

    },

    data() {
        return {
            kossie: 'coder'
            // name: 'Zzee22su'
        }
    },

    methods: {
        // updateName() {
        //     this.name =  'Zzee22su updated';
        // }
    }
}
</script>

<style scoped>
p {
    color: blueviolet;
}
</style>