<template>
    <div id="control-panel">
        <v-container fluid grid-list-lg>
            <v-layout row wrap>
                <v-flex xs12 sm6>
                    <v-text-field label="Solo" single-line solo></v-text-field>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>

<script>
export default {
    name: "ControlPanel"
};
</script>

<style scoped>

</style>
