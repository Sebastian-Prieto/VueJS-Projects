<script setup>
import { ref } from 'vue'
const presupuesto = ref(0);
const definirPresupuesto = () => {
    if(presupuesto.value <= 0)
    console.log('Presupuesto no válido');
}
</script>

<template>
    <form 
        class="presupuesto"
        @submit.prevent="definirPresupuesto"
        >
        <div class="campo">
            <label for="nuevo-presupuesto">Definir presupuesto</label>
            <input 
                type="number"
                id="nuevo-presupuesto" class="nuevo-presupuesto"
                placeholder="Añade tu presupuesto"
                v-model.number="presupuesto"
                min="0"
            />
        </div>

        <input
            type="submit"
            value="Definir presupuesto"
        />
    </form>
</template>

<style scoped>
    .presupuesto {
        width: 100%;
    }

    .presupuesto label {
        font-size: 2.2rem;
        text-align: center;
        color: var(--azul);   
    }
    .campo {
        display: grid;
        gap: 2rem;
    }

    .presupuesto input[type="number"] {
        background-color: var(--gris-claro);
        border-radius: 1rem;
        padding: 1rem;
        border: none;
        font-size: 2.2rem;
        text-align: center;
    }

    .presupuesto input[type="submit"] {
        background-color: var(--azul);
        border: none;
        padding: 1rem;
        text-align: center;
        font-size: 2rem;
        margin-top: 2rem;
        color: var(--blanco);
        font-weight: 900;
        width: 100%;
        cursor: pointer;
    }

    .presupuesto input[type="submit"]:hover {
        background-color: #1048a4;
        transition: background-color 300ms ease;
    }
    
</style>