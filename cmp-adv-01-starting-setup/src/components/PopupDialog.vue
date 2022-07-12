<template>
    <div class="dialog-background" @click.self="$emit('close-dialog')">
    <dialog open>
        <slot></slot>
        <button @click="$emit('close-dialog')">OK</button>
    </dialog>
    </div>
</template>

<script>
</script>

<style scoped>
.dialog-background{
    position: fixed;
    background-color: rgba(0,0,0,0.4);
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
dialog {
    margin: 0;
    width: 30rem;
    max-width: 90%;
    background-color: #fff;
    box-shadow: 0 2px 8px rgba(0,0,0,0.26);
    padding: 1rem;
    position: fixed;
    left: 50%;
    transform: translateX(-50%);
}
</style>