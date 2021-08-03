<template>
    <div class="carousel">
        <slot :currentSlide="currentSlide"/>

        <!-- Navigations -->
        <div class="navigate">
            <div class="toggle-page left">
                <i @click="prevSlide" class="fas fa-chevron-left"></i>
            </div>
            <div class="toggle-page right">
                <i @click="nextSlide" class="fas fa-chevron-right"></i>
            </div>
        </div>

        <!-- Pagination -->
        <div class="pagination">
            <span v-for="(slide, index) in getSlideCount" :key="index">{{ slide }}</span>
        </div>
    </div>
</template>

<script>
import {ref, onMounted} from 'vue'
export default {
    setup(){
        const currentSlide = ref(3) 
        const getSlideCount = ref(null)

        // next slide 
        const nextSlide = ()=>{
            if (currentSlide.value === getSlideCount.value) {
                currentSlide.value =1;
                return;
            }
            currentSlide.value += 1;
        }

        // previous slide 
        const prevSlide = () => {
            if (currentSlide.value === 1) {
                currentSlide.value = 1;
                return;
            }
            currentSlide.value -= 1;

        }
        onMounted(()=> {
            getSlideCount.value = document.querySelectorAll('.slide').length;
            // console.log(getSlideCount.value)
        })
        return {currentSlide, nextSlide, prevSlide, getSlideCount}
    }
}
</script>

<style lang="scss">

.navigate{
    padding:0 16px;
    height:100%;
    width:100%;
    position: absolute;
    display: flex;
    justify-content: center;
    align-items: center
}

.toggle-page{
    display: flex;
    flex: 1;
}

.right{
        justify-content: flex-end;
}

i{
    padding: 10px 13px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    background-color: #6347c7;
    color: #fff
}    
</style>