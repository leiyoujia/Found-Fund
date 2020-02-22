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
    <v-card
        class="tab ma-1"
        hover
    >
        <v-icon
            color="red lighten-1"
            size="60"
        >
            {{ iconName }}
        </v-icon>
        <v-card-text class="font-face text-center pa-0">
            {{ displayText }}
        </v-card-text>
    </v-card>
</template>

<style scoped>
    .tab{
        float: left;
        margin-right:20px;
    }
    .text-center{
        text-align: center;
    }


</style>
