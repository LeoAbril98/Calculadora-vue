<template>
    <div class="display">
        <h2>Resultado: {{ resultado }}</h2>
    </div>
</template>
  
<script>
export default {
    props: {
        resultado: Number,
    },
};
</script>
  
<style scoped>
.display {
    margin-top: 20px;
    color: #fff;
    background-color: #007bff;
    padding: 10px;
    border-radius: 5px;
}
</style>
  