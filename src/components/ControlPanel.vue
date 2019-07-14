<template>
    <div id="control-panel">
        <v-container fluid grid-list-lg>
            <v-expansion-panel>
                <v-expansion-panel-content>
                    <template v-slot:header>
                        <div>Mesh</div>
                    </template>
                    <v-card>
                        <v-card-text>
                            <v-text-field label="Solo" single-line solo></v-text-field>
                        </v-card-text>
                    </v-card>
                    <v-checkbox label="camera fixed"></v-checkbox>
                </v-expansion-panel-content>
            </v-expansion-panel>

            <!-- <v-layout row wrap>
                <v-flex xs12 sm6>
                    <v-text-field label="Solo" single-line solo></v-text-field>
                </v-flex>
            </v-layout> -->
        </v-container>
    </div>
</template>

<script>
export default {
    name: "ControlPanel"
};
</script>