<script>
export default {
    props: {
        // text: String,
        // icon: String,
        left: Boolean,
    }
}
</script>


<template>
    <button>
        <slot v-if="left">Icon Left - Cancel</slot>
        <slot v-else>Submit</slot>
    </button>
</template>

<style>

</style>