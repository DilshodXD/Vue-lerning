<template>
    <div class="d-flex justify-content-end py-3 mx-5">
        <my-button type="button" @click="showModal" class="btn btn-warning mx-5">Add new comment</my-button>
        <my-select v-model="selectedShort" :options="selectOption" class="selct"/>
    </div>
    
    <div style="background: #020202; height: 3px"></div>
</template>

<script>
export default {
    props: {
        showModal: {
            type: Function,
        },
    },
    data() {
        return {
            selectedShort: "",
            selectOption: [
                { value: "name", name: "Filter by name" },
                { value: "email", name: "Filter by email" },
            ],
        };
    },
};
</script>

<style>
.selct {
    width: 180px;
}
</style>