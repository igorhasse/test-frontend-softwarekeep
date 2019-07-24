<template>
    <div class="tabs">
        <div v-for="tab in tabs">
            {{ tab.title }}
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tabs: [
                'teste',
                'vaomo',
                'ajwsdiojasd'
            ]
        }
    }
}
</script>

<style>

</style>
