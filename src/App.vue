<template>
  <div class="flex" v-for="item in products" :key="item">
    <ul class="">

    <li class=" mt-2 text-3xl">{{ item.name
     }}</li>
     <img class="h-[300px]" :src="item.image" alt="">
    </ul>
  
  </div>
</template>
<script >
export default{
data(){

return{
  products:[]
}
console.log(products);
},

 mounted() {
  fetch(' https://api.escuelajs.co/api/v1/categories')
  .then(res=>res.json())
  .then(data=>this.products=data)
  .catch(err=> console.log(err.message))
  // console.log(products);
}
}
</script>