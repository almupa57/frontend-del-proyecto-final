<template>
  <div class="container">
    <form @submit.prevent="handleSubmit()">
        <h2>Busca presupuestos con el nit de tu empresa</h2>
        <input type="number" name="nit" placeholder="Nit " v-model="nit" />
        <input class="btn" type="submit" value="Buscar presupuesto" />
    </form> 
    <hr>

    <h5>{{ response ? null : 'Sorry, no encontramos tu nit' }}</h5>

    <div class="resultado" v-for="(presupuesto, index) in response" :key="index">
        <h5>Nombre: {{ presupuesto.nombreEmpresa }}</h5>
        <h5>{{`Tomas: ${presupuesto.tomaCant} ------------------- ${presupuesto.puToma * presupuesto.tomaCant}$ `}}</h5>
        <h5>{{`Luces: ${presupuesto.cantidadLuces} ------------------- ${presupuesto.puLuces * presupuesto.cantidadLuces}$ `}}</h5>
        <h5>{{`Interruptores: ${presupuesto.cantidadInterruptores} ----------- ${presupuesto.puInterruptores * presupuesto.cantidadInterruptores}$ `}}</h5>
        <h5>ToTal: {{presupuesto.total}}</h5>
    </div>
     
  </div>
</template>


<script>
import axios from "axios";

export default {
  data() {
    return {
      nit: null,
      response: [],
    };
  },

  methods: {
    async  handleSubmit() {
     console.log(this.nit);  
     
      const url = `https://presupuesto-api.herokuapp.com/presupuesto/${this.nit}`;

      try {

        const response = await axios.get(url, {
          nit: this.nit,
        });
        this.response = response.data.presupuestos    

        console.log(response.data.presupuestos);

      } catch (error) {
        console.error(error);
      } 
    },
  },
};
</script>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: relative;
    padding: 20px;
    bottom: 80px;
}

form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

input {
    height: 30px;
    width: 80%;
    margin-bottom: 15px;
}

.btn {
  width: 40%;
  height: 35px;
  padding: 10px;
  color: white;
  font-weight: 700;
  background: #334979;
  border-radius: 15px;
  border: none;
}

hr {
    width: 90%;
}

.resultado {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 20px;
    margin-bottom: 20px;
    -webkit-box-shadow: 5px 7px 11px -4px rgba(0,0,0,0.82); 
    box-shadow: 5px 7px 11px -4px rgba(0,0,0,0.82);
}

h5 {
    margin: 5px;
}

</style>