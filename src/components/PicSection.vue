<template>
    <section class="framework">
        <h3>{{ title }}</h3>
        <div>
            <img :src="image">
            <br>
            <p>{{ description }}</p>
        </div>

    </section>
</template>

<script setup lang="ts">
interface Props {
    id?: string
    title?: string
    image?: string
    description?: string
}

const { props } = defineProps<{ props: Props }>()
const title = props.title
const image = (props.image || "").startsWith("assets") ? new URL(`../${props.image}`, import.meta.url).href : props.image
const description = props.description
</script>

<style lang="scss" scoped>
.framework {
    * {
        max-width: 960px;
        @apply w-full;
    }

}
</style>
