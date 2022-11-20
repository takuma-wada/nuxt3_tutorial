<template>
    <div>
        Counter: {{ counter }}
        <button @click="counter++">
            +
        </button>
        <button @click="counter--">
            -
        </button>
    </div>
    <div>
        Double Counter: {{ doubleCount }}
    </div>
</template>

<script setup lang="ts">import { Ref } from 'vue';

const counter: Ref<number> = useState('counter', () => 500)

const inputNumber: Ref<number> = ref(0)

const onClickButton = () => {
    counter.value = inputNumber.value
}
const doubleCount = computed(() => {
    return counter.value * 2
})

watch(counter, (count, prevCount) => { alert(counter.value) })

</script>