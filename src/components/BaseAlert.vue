<template>
    <div :class="baseClass">
        <slot/>
        <spam style="margin-right: 5px;">
            x
        </spam>
    </div>
</template>

<script>
export default {
    props: {
        variant: {
            type: String,
            default: ''
        },
    },

    methods: {
        
    },
    computed: {
        baseClass() {
            return [
                'alert',
                this.variant ? `alert-${this.variant}` : ''
            ]
        },
    },

}
</script>

<style scoped>
.alert {
    display: flex;
    justify-content: space-between;
    padding: 5px;
    border-radius: 6px;
    color: gray;
    background: #ddd;
}
.alert-success {
    background: #2c3e50;
    color: #fff;
}
.alert-danger {
    background: red;
    color: #fff;
}
</style>