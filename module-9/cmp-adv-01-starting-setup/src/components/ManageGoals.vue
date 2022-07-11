<template>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal">
    <button @click="setGoal">Set Goal</button>
    <teleport to="body">
        <PopupDialog v-if="inputInvalid" @close-dialog="closeError">
                <h2>Please Enter a value</h2>
        </PopupDialog>
    </teleport>
</template>

<script>
import PopupDialog from './PopupDialog.vue';
export default {
    data() {
        return {
            inputInvalid: false
        }
    },
    methods: {
        setGoal() {
            const enteredValue = this.$refs.goal.value;
            if (enteredValue == '') {
                this.inputInvalid = true
            }
        },
        closeError() {
            this.inputInvalid = false
        }
    },
    components: {
        PopupDialog
    }
}
</script>

<style lang="scss" scoped>
</style>