<template>
    <div v-if="isVisible">
<ul>
 <template v-for="fruit in fruits " :key="fruit" >
    <li v-if="fruit === 'banana'" >{{ fruit }}</li>
 </template>
        
</ul>


<ul>
    <li v-for="car,key in cars" :key="key"> {{ key}}
    </li>
</ul>
    </div>
</template>

<script>
    export default {
        name: 'DirectiveTest',
        data(){
            return {
                isVisible: true,
                fruits: ['kiwi', 'banana', 'apple'],
                cars: {
audi:{
    color:"red"
},
bmw: {
    color: "black"
}
                }
            }
        }
    }
</script>

<style scoped>

</style>