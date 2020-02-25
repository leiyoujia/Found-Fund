<template>
    <v-data-table
        :headers="headers"
        :items="funds"
        :sort-by="['calories', 'fat']"
        :sort-desc="[false, true]"
        multi-sort
        class="elevation-1"
    ></v-data-table>
</template>

<script>

export default {
    name: "FundTable",
    props: {
        funds: { type: Array, require: true },
    },
    data: () => ({
        headers: [
            {
                text: "index",
                align: "left",
                sortable: false,
                value: "index",
            },
            { text: "fundId", value: "fundId" },
            { text: "shortName", value: "shortName" },
            { text: "link", value: "link" },
            { text: "perPrice", value: "perPrice" },
            { text: "totalPrice", value: "totalPrice" },
            { text: "totalPrice", value: "totalPrice" },
            { text: "totalPrice", value: "totalPrice" },
            { text: "totalPrice", value: "totalPrice" },
        ],
    }),
    created() {
        // this.getFundList();
    },
    methods: {
        // getFundList() {
        //     fund.getAll().then((result) => {
        //         result.forEach((item, index) => {
        //             this.funds[index] = {
        //                 index,
        //                 fundId: item[0],
        //                 shortName: item[2],
        //             };
        //         });
        //     });
        // },
    },
};
</script>

<style scoped>

</style>
