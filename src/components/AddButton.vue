<template>
 <button class="add-btn">
    <i class="fa-solid fa-plus"></i>
 </button>
</template>

<script> 

</script>

<style scoped>
.add-btn {
   position: fixed ;
   right: 20px;
   bottom:20px; 
   width: 68px;
   height: 68px;
   border-radius: 50;
   border: 4px solid;
   font-size: 30px;
   cursor: pointer;
   transition: 300ms ;
}
.add-btn:hover{
   background-color:rgba(0, 191, 255, 0.84);
   transform: scale(1.2);
}
</style>