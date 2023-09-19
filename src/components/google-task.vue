<template>
    <div id="container" class="max-w-xs mx-auto mt-24 relative">
        <span class="mt-20 flex items-center relative">
            <input type="text"
                class="w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-4 px-5 text-2xl font-bold"
                placeholder="Add Title" @keypress.enter="addSubTitle">
            <i class="fa-solid fa-circle-plus text-rose-500 text-2xl absolute right-1 cursor-pointer"
                @click="addSubTitle"></i>
        </span>
        <!-- <input type="text"
            class="mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold">
        <i class="fa-solid fa-circle-plus text-rose-500 text-2xl absolute -right-5 bottom-4 cursor-pointer"></i> -->
    </div>
</template>

<script>
export default {
    methods: {
        addSubTitle() {
            let subTitle = document.createElement("input")
            let icon = document.createElement("i")
            icon.className = "fa-solid fa-circle-plus text-rose-500 text-2xl absolute -right-5 bottom-4 cursor-pointer"
            subTitle.className = "mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold"
            const parent = document.getElementById("container")
            parent.append(subTitle)
            parent.append(icon)
            subTitle.focus()
            subTitle.addEventListener("keypress", (event) => {
                if (event.keyCode === 13) {
                    this.addMultipleSubTitle()
                }
            })
        },
        addMultipleSubTitle() {
            let subTitle = document.createElement("input")
            let icon = document.createElement("i")
            subTitle.className = "mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold"
            icon.className = "fa-solid fa-circle-plus text-rose-500 text-2xl absolute -right-5 bottom-4 cursor-pointer"
            const parent = document.getElementById("container")
            parent.append(subTitle)
            parent.append(icon)
            subTitle.focus()
            subTitle.addEventListener("keypress", (event) => {
                if (event.keyCode === 13) {
                    this.addSubTitle()
                }
            })
        }
    }
}
</script>

<!-- <script setup>
const parent = document.getElementById("container")
const subTitle = document.createElement("input")
subTitle.className = "mt-6 ml-4 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold"
const addSubTitle = () => {
    parent.append(subTitle)
    subTitle.focus()
}

subTitle.addEventListener("keypress", (event) => {
    if (event.keyCode === 13) {
        addSubTitle()
    }
})
</script> -->