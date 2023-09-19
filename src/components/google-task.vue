<template>
    <div id="container" class="max-w-md mx-auto mt-24 relative">
        <span class="mt-20 flex items-center relative">
            <input type="text"
                class="w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-4 px-5 text-2xl font-bold"
                placeholder="Add Title" @keypress.enter="addSubTitle">
            <i class="fa-solid fa-circle-plus text-rose-500 text-2xl absolute right-1 cursor-pointer"
                @click="addSubTitle"></i>
        </span>
        <!-- <span class="mt-6 ml-8 flex items-center">
            <input type="text"
                class="mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold">
            <i class="fa-solid fa-circle-plus text-rose-500 text-2xl cursor-pointer -ml-5"></i>
        </span> -->
        <!-- <input type="text"
            class="mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold">
        <i class="fa-solid fa-circle-plus text-rose-500 text-2xl absolute -right-5 bottom-4 cursor-pointer"></i> -->
    </div>
</template>

<script>
export default {
    methods: {
        addSubTitle() {
            let span = document.createElement("span")
            let subTitle = document.createElement("input")
            let icon = document.createElement("i")
            span.className = "mt-6 ml-8 flex items-center subTitle"
            icon.className = "fa-solid fa-circle-minus text-rose-500 text-2xl cursor-pointer -ml-5"
            subTitle.className = "mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold"
            const parent = document.getElementById("container")
            parent.append(span)
            span.append(subTitle)
            span.append(icon)
            subTitle.focus()
            subTitle.addEventListener("keypress", (event) => {
                if (event.keyCode === 13) {
                    this.addMultipleSubTitle()
                }
            })
            subTitle.addEventListener("keydown", (event) => {
                if (event.key === "Backspace") {
                    if (subTitle.value.length < 1) {
                        subTitle.parentElement.remove()
                        const lists = document.getElementsByClassName("subTitle")
                        // console.log(lists);
                        if (lists.length > 0) {
                            parent.lastChild.querySelector("input").focus()
                        } else if (lists.length == 0) {
                            parent.firstChild.querySelector("input").focus()
                        }
                    }
                }
                // console.log(event);
            })
            icon.addEventListener("click", () => {
                icon.parentElement.remove()
            })
        },
        addMultipleSubTitle() {
            let span = document.createElement("span")
            let subTitle = document.createElement("input")
            let icon = document.createElement("i")
            span.className = "mt-6 ml-8 flex items-center subTitle"
            subTitle.className = "mt-6 ml-8 w-full border-b-2 focus:border-rose-500 inline-block mx-auto outline-none py-2 px-3 text-xl font-semibold"
            icon.className = "fa-solid fa-circle-minus text-rose-500 text-2xl cursor-pointer -ml-5"
            const parent = document.getElementById("container")
            parent.append(span)
            span.append(subTitle)
            span.append(icon)
            subTitle.focus()
            subTitle.addEventListener("keypress", (event) => {
                if (event.keyCode === 13) {
                    this.addSubTitle()
                }
            })
            subTitle.addEventListener("keydown", (event) => {
                if (event.key === "Backspace") {
                    if (subTitle.value.length < 1) {
                        subTitle.parentElement.remove()
                        const lists = document.getElementsByClassName("subTitle")
                        // console.log(lists);
                        if (lists.length > 0) {
                            parent.lastChild.querySelector("input").focus()
                        } else if (lists.length == 0) {
                            parent.firstChild.querySelector("input").focus()
                        }
                    }
                }
                // console.log(event);
            })
            icon.addEventListener("click", () => {
                icon.parentElement.remove()
            })
        }
    }
}
</script>
