<template>
    <div class="text-center">
        <h2 class="text-3xl font-bold">{{text}}</h2>
        <div class="mt-4 mb-10 text-2xl">{{dataDate}}</div>
    </div>

</template>

<script>
export default {
    name: 'DataTitle',
    props: ['text', 'dataDate']
}
</script>