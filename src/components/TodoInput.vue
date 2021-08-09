<template>
    <div class="mb-5">
        <h3>Vue.js To-Do App</h3>
      </div>
      <div class="mb-3">
        <input v-model="inputData" @keydown.enter="pushData" type="text" class="form-control" id="addTask" placeholder="Add Task">
    </div>
</template>

<script>
    export default {
        inject: {
            providedData: {
                type: Object,
                required: true
            }
        },
        data() {
            return {
                inputData: ""
            }
        },
        methods: {
            pushData(e) {
                const newItem = {
                    id: new Date().getDate,
                    text: e.target.value
                }
                this.providedData.taskList.push(newItem);
                this.inputData = ""
            }
        }
    }
</script>