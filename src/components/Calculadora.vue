<template>

    <div class="container">
        <h1>Calculadora Aritmética</h1>
        <div class="calculadora">
            <input type="number" v-model="numero1" @input="calculate" />
            <input type="number" v-model="numero2" @input="calculate" />

            <select v-model="operacao" @change="calculate">
                <option value="adicao">+</option>
                <option value="subtracao">-</option>
                <option value="multiplicacao">*</option>
                <option value="divisao">/</option>
            </select>
        <div>Resultado: {{ resultado }}</div>
    </div>
    
    </div>
</template>

<script>
    export default {
        data() {
            return {
            numero1: 0,
            numero2: 0,
            operacao: 'adicao',
            resultado: 0
            };
        },
        methods: {
            calculate() {
                switch (this.operacao) {
                    case 'adicao':
                        this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
                        break;
                    case 'subtracao':
                        this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
                        break;
                    case 'multiplicacao':
                        this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
                        break;
                    case 'divisao':
                        if (this.numero2 != 0) {
                        this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
                        } else {
                        this.resultado = 'teste';
                        }
                        break;
                }
            }
        },
        mounted() {
            this.calculate();
        }
    }
</script>

<style>
    .container, h1 {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    h1 {
        text-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .calculadora {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 15px; 
        padding: 20px;
        border: 1px solid black;
        border-radius: 10px;
        width: 100%;
        max-width: 300px; 
       
    }

    input, select {
        box-sizing: border-box;
        width: 100%;
        padding: 10px;
        border: 1px solid black;
        border-radius: 5px;
        font-size: 16px;
    }

    select {
        width: 50%;
        text-align-last: center; 
    }  

    .calculadora, input, select {
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    @media (max-width: 390px) {
    .calculadora {
        gap: 8px; 
        padding: 10px; 
    }

    h1 {
        font-size: 16px; 
        margin-bottom: 10px; 
    }

    input, select {
        padding: 5px; 
        font-size: 14px; 
    }

    select {
        width: 70%;
    } 
}
</style>
