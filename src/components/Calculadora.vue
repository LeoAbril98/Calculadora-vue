<template>
    <div class="calculadora">
        <input type="number" v-model.number="numero1" @input="calcular" class="input-numero">
        <select v-model="operacao" @change="calcular" class="select-operacao">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>
        <input type="number" v-model.number="numero2" @input="calcular" class="input-numero">
        <Display :resultado="resultado" />
    </div>
</template>
  
<script>
import Display from './Display.vue';

export default {
    components: {
        Display,
    },
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: '+',
        };
    },
    computed: {
        resultado() {
            switch (this.operacao) {
                case '+':
                    return this.numero1 + this.numero2;
                case '-':
                    return this.numero1 - this.numero2;
                case '*':
                    return this.numero1 * this.numero2;
                case '/':
                    return this.numero1 / this.numero2;
                default:
                    return 0;
            }
        },
    },
    methods: {
        calcular() {
            // Nada a fazer aqui, pois os cálculos são realizados automaticamente através de v-model e @input
        },
    },
};
</script>
  
<style scoped>
.calculadora {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.input-numero,
.select-operacao {
    margin: 5px;
    padding: 5px;
    border-radius: 5px;
    border: 1px solid #ccc;
}

.input-numero:focus,
.select-operacao:focus {
    outline: none;
}

.display {
    margin-top: 20px;
    color: #fff;
    background-color: #007bff;
    padding: 10px;
    border-radius: 5px;
}
</style>
  