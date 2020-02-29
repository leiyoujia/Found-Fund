<template>
    <v-data-table
        :headers="headers"
        :items="funds"
        :page="20"
        :items-per-page="20"
        :sort-by="['calories', 'fat']"
        :sort-desc="[false, true]"
        multi-sort
        class="elevation-1"
    />
</template>

<script>
import { toNumber, round } from "lodash";
import Fund from "../services/fund";

export default {
    name: "FundTable",
    data: () => ({
        groupBy: ["10", "20", "50"],
        headers: [
            {
                text: "index",
                align: "left",
                sortable: false,
                value: "index",
            },
            { text: "symbol", value: "symbol" },
            { text: "shortName", value: "shortName" },
            { text: "perPrice", value: "perPrice" },
            { text: "totalPrice", value: "totalPrice" },
            { text: "return", value: "return" },
            { text: "returnRate", value: "returnRate" },
            { text: "status", value: "status" },
            { text: "fee", value: "fee" },
            { text: "operate", value: "operate" },
        ],
        funds: [],
    }),
    mounted() {
        this.headers.forEach((item) => {
            // eslint-disable-next-line no-param-reassign
            item.text = this.$t(`labels.headers.${item.text}`);
        });

        Fund.getMarketValues().then((result) => {
            this.funds = result.map((item, index) => {
                /* eslint-disable camelcase */
                const {
                    symbol, sname, per_nav, total_nav, nav_a, nav_rate, sg_states,
                } = item;
                /* eslint-enable camelcase */
                return {
                    index: index + 1,
                    symbol,
                    shortName: sname,
                    perPrice: round(toNumber(per_nav), 4),
                    totalPrice: round(toNumber(total_nav), 4),
                    return: round(toNumber(nav_a), 4),
                    returnRate: `${round(toNumber(nav_rate), 2)}%`,
                    status: sg_states,
                    operate: this.$t("action.collect"),
                };
            });
        });
    },
};
</script>

<style scoped>

</style>
