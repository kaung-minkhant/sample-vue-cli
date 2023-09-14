<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{sale: theme==='sale'}">
            <slot>This is default</slot>

            <div class="links">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background-color: white;
    border-radius: 10px;
}

.modal.sale {
    background-color: crimson;
    color: white;
}

.modal.sale h1 {
    color: white
}

.modal .links {
    text-align: center;
    margin: 30px 0 10px 0;
}

.modal .links a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
.backdrop {
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

p {
    font-style: normal;
}
</style>