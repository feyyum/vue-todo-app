<template>
    <div class="mb-3">
        <div class="list-group">
          <button v-for="item in providedData.taskList" :key="item.id" @click.prevent="deleteOne(item)" type="button" class="list-group-item list-group-item-action mb-2" style="background-color: lightgray;">{{ item.text }}</button>
        </div>
      </div>
      <div class="row mb-3 g-3">
        <p class="col-md-8">Click to task for delete.</p>
        <button class="btn btn-danger col-md-4" @click.prevent="deleteAll">Clear All</button>
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
        methods: {
            deleteAll() {
                this.providedData.taskList = [];
            },
            deleteOne(item) {
                this.providedData.taskList = this.providedData.taskList.filter(t => t != item);
            }
        }
    }
</script>