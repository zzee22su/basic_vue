<template>
    <div>
        <p>
            {{ name }}
        </p>
        <button @click="updateName">
            Change Name
        </button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: 'Zzee22su'
        }
    },

    methods: {
        updateName() {
            this.name =  'Zzee22su updated';
        }
    }
}
</script>

<style scoped>
</style>