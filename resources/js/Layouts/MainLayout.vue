<template>
    <Link href="/">Main Page</Link>&nbsp;
    <Link href="/hello">Show Page</Link>
    <!-- <div>The page with time {{ timer }}</div> -->
    <div v-if="flashSuccess" class="success">
        {{ flashSuccess }}
    </div>
    <slot></slot>
</template>

<script setup>
    import {computed} from 'vue' 
    import {Link, usePage} from '@inertiajs/vue3'
    // import {ref} from 'vue'

    // page.props.value.flash.success
    const page = usePage()
    const flashSuccess = computed(
        () => page.props.flash.success,
    )
    
    // const timer = ref(0)
    // setInterval(()=>timer.value++, 1000)
</script>

<style scoped>
    .success{
        background-color: green;
        color: white;
    }
</style>