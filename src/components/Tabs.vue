<script setup>
import { useSlots, ref , provide, onMounted} from 'vue'
import { useRoute, useRouter }from 'vue-router';

const route = useRoute();
const router = useRouter()
const slots = useSlots()
const tabTitles = ref(slots.default().map(tab => tab.props.title))
const selectedTitle = ref(tabTitles.value[0])

provide('selectedTitle', selectedTitle)


function setTabActive(tabTitle){
    selectedTitle.value = tabTitle
   router.push({ hash:'#' + tabTitle })
}

onMounted(()=>{
  const { hash }  = route
  if(hash) {
    setTabActive(hash.split('#')[1])
  } else {
    setTabActive(selectedTitle.value)
  }

})
</script>



<template>
    <div class="tabs">

        <ul class="tabs__header">

            <li 
                v-for="title in tabTitles" 
                :key="title"
                class="tabs__item"
                :class="{ selected: selectedTitle === title}"
                @click="setTabActive(title)"
            >
                {{ title }}
            </li>

        </ul>

        <slot />
    </div>
</template>

<style>
.tabs {
    max-width: 60vw;
    margin: 0 auto;
}

.tabs__header {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    justify-content: space-between;
    gap: 5px;
}

.tabs__item {
    flex: 1;
    background-color: #eee;
    padding: 5px 0;
    border-radius: 5px 5px 0 0;
    transition: .4s all ease-out;
    cursor: pointer;
    user-select: none;
}

.tabs__item.selected {
    background-color: #bfbfbf;
}

</style>