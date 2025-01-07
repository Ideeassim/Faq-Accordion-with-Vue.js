<script setup>

import data from "../Data/que-ans.json"
import { ref } from "vue";


const info=ref(data)





</script>

<template>
    <picture class="bg-top">
        <source media="(min-width: 768px)" srcset="../../faq-accordion-main/assets/images/background-pattern-desktop.svg">
        <!-- mobile -->
        <img src="../../faq-accordion-main/assets/images/background-pattern-mobile.svg" alt="">       
    </picture>
    <div class="faq">
        <div class="heading">
            <img src="../../faq-accordion-main/assets/images/icon-star.svg" alt="">
            <h1>FAQs</h1>           
        </div>

        <div>
            <div  v-for="(i) in info" :key="i.id" :id="i.id" :data="i" class="text">
                <div class="icon-div" >
                    <h3>{{ i.Question }}</h3> <img v-if="!i.state"  @click="i.state=true" src="../../faq-accordion-main/assets/images/icon-plus.svg">
                    <img v-if="i.state" src="../../faq-accordion-main/assets/images/icon-minus.svg" alt="" @click="i.state=false" > 
                </div>
                <p v-if="i.state">{{ i.Answer }}</p>
                <hr>
            </div>
        </div>
    </div>
</template>

<style scoped>

.heading{
    display: flex;
    gap: 1rem;
}
.heading h1{
    font-size: 3rem;
    color: rgb(48, 21, 52);
}
.faq{
   
    border-radius: 10px;
    width: 32.5rem;
    height: auto;
    margin: 0 auto;
    padding: 25px;
    background-color: #ffffff;
    margin-bottom: 10rem;
    position: absolute;
    top: 43%;
    left: 30%;
}

.text>p{
    color: rgb(139, 105, 145);
    font-size: 18px;
    line-height: 30px;
}
.icon-div{
    display: flex;
    justify-content: space-between;
}
.icon-div>h3{
    cursor: pointer;
    
   
}
.icon-div>h3:hover{
    color: #AD28EB;
}
.icon-div>img{
    cursor: pointer;
}

@media (min-width: 320px) and (max-width: 480px) {
  
  /* CSS */
  .faq{
    height: auto;
    width: 15rem;
    
    left: 10%;
    top: 20%;
  }
  .heading>h1{
    font-size: 2rem;
  }
.icon-div>h3{
    font-size: 1.1rem;
    width: 500px;
}
.text>p{
    font-size: 0.5rem;
    line-height: 10px;
}
.icon-div>img{
    height: 30px;
    padding-top: 10px;
}
}
</style>
