<template>
    <div class="bvm-clusters">
        <v-btn
            depressed
            large
            tile
            class="mt-1"
            color="blue lighten-1 white--text"
            @click="insertCluster">
            Insert
        </v-btn>

        <v-data-table
            :headers="[]"
            :items="[]"
            multi-sort
            hide-default-footer
            class="mt-2 elevation-1"
        />
    </div>
</template>
<script>
export default {
    created() {
        this.$request.get("api/cluster/all");
    },
    methods: {
        insertCluster() {
            this.$request.post("api/cluster/add", {
                name: "cluster",
                metadataServiceUri: "test"
            });
        }
    }
};
</script>
