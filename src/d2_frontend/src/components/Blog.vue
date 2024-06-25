<template>
    <div>
        <button @click="pobierzWpisy">refresh</button>
        siema blog!
        {{ wpisy }}
    </div>
</template>

<script>
import { d2_backend } from 'declarations/d2_backend/index';

export default {
    data() {
        return {
            wpisy: []
        }
    },
    methods: {
        async pobierzWpisy() {
            this.wpisy = await d2_backend.odczytaj_wpisy();
        }
    },
}
</script>