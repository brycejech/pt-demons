<template lang="html">
    <div id="signup-component">
        <h3 class="text-center">Bandit Football Signup</h3>
        <form id="signup-form" @submit.prevent="submit">
            <div class="row">
                <div class="col-6">
                    <label for="player-first-name">Player First Name</label>
                    <input id="player-first-name" type="text" v-model="player.firstName">
                </div>
                <div class="col-6">
                    <label for="player-last-name">Player Last Name</label>
                    <input id="player-last-name" type="text" v-model="player.lastName">
                </div>
                <div class="col-6">
                    <label for="player-dob">Player Date of Birth</label>
                    <input id="player-dob" type="text" v-model="player.dob">
                </div>
                <div class="col-6">
                    <label for="player-grade">Player Grade</label>
                    <select id="player-grade">
                        <option v-for="grade in grades" :value="grade.value">{{ grade.label }}</option>
                    </select>
                </div>
                <div class="col-6">
                    <label for="player-school">Player School</label>
                    <input id="player-school" type="text" v-model="player.school">
                </div>
            </div>
        </form>
    </div>
</template>

<script>
'use strict';

export default {
    name: 'sign-up-form',
    data() {
        return {
            player: {
                firstName: '',
                lastName:  '',
                dob:       '',
                grade:     '',
                school:    '',
                address:   '',
                city:      ''
            },
            parent: {
                firstName: '',
                lastName:  '',
                homePhone: '',
                cellPhone: '',
                email:     ''
            },
            date: new Date(),
            grades: [
                { value: 4, label: '4th' },
                { value: 5, label: '5th' },
                { value: 6, label: '6th' },
                { value: 7, label: '7th' },
                { value: 8, label: '8th' }
            ],
            campEnrollment: false,
            campShirtSize: '',
            campShirtSizes: [
                // Youth sizes
                'YS', 'YM', 'YL', 'YXL',
                // Adult sizes
                'AS', 'AM', 'AL', 'AXL', 'AXXL', 'AXXXL'
            ]
        }
    },
    submit(){
        console.log(this.data);
    }
}

</script>

<style lang="sass" scoped>

</style>
