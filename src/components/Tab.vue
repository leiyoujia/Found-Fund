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
            return this.$t(this.text);
        },
    },
};
</script>

<template>
    <v-card hover>
        <v-icon
            color="red lighten-1"
            size="80"
        >
            {{ iconName }}
        </v-icon>
        <v-card-text class="pa-2">
            <span class="font-face">
                {{ displayText }}
            </span>
        </v-card-text>
    </v-card>
</template>

<style scoped>

</style>
