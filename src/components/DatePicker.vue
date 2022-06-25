<template>
    <div>
        <v-row>
            <v-col cols="12" sm="6" md="4">
                <v-menu v-model="menu" :close-on-content-click="false" :nudge-right="40" transition="scale-transition"
                    offset-y min-width="auto">
                    <template v-slot:activator="{ on, attrs }">
                        <v-text-field v-model="dateRangeText" readonly></v-text-field>
                        <v-btn v-bind="attrs" v-on="on">&or;</v-btn>
                    </template>
                    <v-date-picker v-model="dates" range dark show-week >
                    <v-btn @click="menu = false" >ok</v-btn> <v-btn @click="menu = false" >close</v-btn></v-date-picker>
                </v-menu>
            </v-col>
        </v-row>
    </div>
</template>


<script>
import moment from 'moment'
export default {
    data: () => ({
        dates: [],
        menu: false,
        modal: false,
    }),
    computed: {
        dateRangeText() {
            return this.dates.join(' - ')
        },
    },
    mounted() {
        this.setRange()
        this.getDay()
    },
    methods: {
        getDay() {
            let m = moment().day()
            return m
        },
        setRange() {
            let start = moment().subtract(2, 'days').format('YYYY-MM-DD')
            let end = moment().add(2, 'days').format('YYYY-MM-DD')
            this.dates = [start, end]
        }
    }
}
</script>