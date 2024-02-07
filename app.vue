<template>
    <UContainer class="max-w-screen-sm mx-auto mt-64">
        <UCard>
            <template #header>
                List
            </template>
            <UInput
                v-model="input"
                @keypress="insert_todo"
            />
            <UDivider
                label="LIST"
                class="py-4"
            />
            <div
                v-for="todo in todo_list"
            >
                <p>{{ todo }}</p>
            </div>
        </UCard>
    </UContainer>
</template>

<script setup lang="ts">
    const input = ref('');
    const todo_list = ref(<string[]>[]);

    function insert_todo (e) {

        // user presses enter
        if (e.keyCode === 13) {
            todo_list.value.push(input.value);

            input.value = '';
        }

    }
</script>