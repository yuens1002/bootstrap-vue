<template>
    <a :is="itemType"
       :class="[dropdown-item,{ disabled: disabled}]"
       :to="to"
       :href="hrefString"
       :disabled="disabled"
       :tabindex="disabled ? '-1' : '0'"
       @click="click"
    ><slot></slot></a>
</template>

<script>
    import bLink from './link.vue';

    export default {
        extends: bLink,
        computed: {
            itemType() {
                return (this.href || this.to) ? this.componentType : 'button';
            }
        }
    };
</script>
