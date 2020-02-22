<script>
export default {
    name: "NavTab",
    props: {
        icon: { type: String, require: true },
        text: { type: String, require: true },
    },
    computed: {
        iconName() {
            return `mdi-${this.icon}`;
        },
        displayText() {
            return this.$t(`labels.${this.text}`);
        },
    },
};
</script>

<template>
    <v-card class="ma-2" hover>
        <v-icon
            color="red lighten-1"
            size="60"
        >
            {{ iconName }}
        </v-icon>
        <v-card-text class="pa-0">
            <span class="font-face">
                {{ displayText }}
            </span>
        </v-card-text>
    </v-card>
</template>

<style scoped>

</style>
