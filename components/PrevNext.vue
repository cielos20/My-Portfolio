<template>
    <div>
        <NuxtLink v-if="prev" :to="{name: 'blog-slug', params: {slug: prev.slug}}" class="font-weight-bold primary--text">
            {{prev.title}}
        </NuxtLink>
        <span v-else>&nbsp;</span>
        <NuxtLink v-if="next" :to="{ name: 'blog-slug', params: { slug: next.slug } }" class="font-weight-bold primary--text">
        {{ next.title }}
        </NuxtLink>
        <span v-else>&nbsp;</span>
    </div>
</template>

<script>
export default {
    props: {
        prev: {
            type: Object,
            default: () => null
        },
        next: {
            type: Object,
            default: () => null
        }
    }
}
</script>