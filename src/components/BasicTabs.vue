<template>
    <div>
        <div>
            <div class="tabs">
                <button 
                    class="tab-item"
                    @click="switchTab('Tab1')">
                    Tab1
                </button>
                <button 
                    class="tab-item"
                    @click="switchTab('Tab2')">
                    Tab2
                </button>
            </div>
            <KeepAlive>
                <component :is="currentTabComponent" :key="tabKey" />
            </KeepAlive>
        </div>
    </div>
</template>


<script setup>
import Tab1 from './tabs/Tab1.vue';
import Tab2 from './tabs/Tab2.vue';
import {shallowRef, ref} from 'vue';

const tabs = {
    'Tab1': Tab1,
    'Tab2': Tab2,
}

const tabKey = ref('Tab1');

const currentTabComponent = shallowRef(tabs[0]);

function switchTab(key) {
    currentTabComponent.value = tabs[key];
    tabKey.value = key;
}
</script>