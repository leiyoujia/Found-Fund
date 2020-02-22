<script>
import NavDrawers from "./components/NavDrawers.vue";
import NavTab from "./components/Tab.vue";

export default {
    components: {
        NavDrawers,
        NavTab,
    },
    data: () => ({
        drawer: null,
        tabList: {
            price: "chart-bar",
            estimation: "chart-line",
            ranking: "format-list-numbered",
            optional: "clipboard-plus-outline",
            fundBar: "comment-multiple-outline",
            account: "account-check-outline",
            trade: "currency-usd-circle-outline",
            buy: "cart-plus",
            current: "home-currency-usd",
            vip: "credit-card-settings-outline",
        },
    }),
    created() {
        this.$vuetify.theme.light = true;
    },
};
</script>

<template>
    <v-app id="found-fund">
        <v-navigation-drawer
            v-model="drawer"
            app
            clipped
        >
            <nav-drawers />
        </v-navigation-drawer>

        <v-app-bar
            app
            clipped-left
            color="red"
            dense
        >
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
            <v-icon class="mx-4">
                fab fa-youtube
            </v-icon>
            <v-toolbar-title class="mr-12 align-center">
                <span class="title font-face">
                    {{ $t("title") }}
                </span>
            </v-toolbar-title>
            <v-spacer />
            <v-row
                align="center"
                style="max-width: 650px"
            >
                <v-text-field
                    :append-icon-cb="() => {}"
                    placeholder="Search..."
                    single-line
                    append-icon="search"
                    color="white"
                    hide-details
                />
            </v-row>
        </v-app-bar>

        <v-content>
            <v-container class="fill-height">
                <nav-tab
                    icon="chart-bar"
                    text="labels.price"
                />
            <!--                <v-row-->
            <!--                    justify="center"-->
            <!--                    align="center"-->
            <!--                >-->
            <!--                    <v-col class="shrink">-->
            <!--                        <v-tooltip right>-->
            <!--                            <template v-slot:activator="{ on }">-->
            <!--                                <v-btn-->
            <!--                                    :href="source"-->
            <!--                                    icon-->
            <!--                                    large-->
            <!--                                    target="_blank"-->
            <!--                                    v-on="on"-->
            <!--                                >-->
            <!--                                    <v-icon large>-->
            <!--                                        mdi-code-tags-->
            <!--                                    </v-icon>-->
            <!--                                </v-btn>-->
            <!--                            </template>-->
            <!--                            <span>Source</span>-->
            <!--                        </v-tooltip>-->
            <!--                        <v-tooltip right>-->
            <!--                            <template v-slot:activator="{ on }">-->
            <!--                                <v-btn-->
            <!--                                    icon-->
            <!--                                    large-->
            <!--                                    href="https://codepen.io/johnjleider/pen/aezMOO"-->
            <!--                                    target="_blank"-->
            <!--                                    v-on="on"-->
            <!--                                >-->
            <!--                                    <v-icon large>-->
            <!--                                        mdi-codepen-->
            <!--                                    </v-icon>-->
            <!--                                </v-btn>-->
            <!--                            </template>-->
            <!--                            <span>Codepen</span>-->
            <!--                        </v-tooltip>-->
            <!--                    </v-col>-->
            <!--                </v-row>-->
            </v-container>
        </v-content>
    </v-app>
</template>

<style lang="scss">
/*.theme--light.v-sheet {*/
/*    color: azure;*/
/*}*/

#found-fund {
    .font-face {
        font-family: "Noto Sans SC" !important;
    }
}

</style>
