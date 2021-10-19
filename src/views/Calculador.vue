<template>
  <div class="container">
    <form class="form" @submit.prevent="handleSubmit()">
      <h2>Ingresa algunos datos</h2>

      <label for="nombre">Nombre de la empresa</label>
      <input type="text" name="nombre" placeholder="Nombre" v-model="nombre" />

      <label for="nit">Nit de la empresa</label>
      <input type="number" name="nit" placeholder="Nit " v-model="nit" />

      <label for="tipo">Elige un tipo de vivienda</label>
      <select name="tipo" v-model="tipo" @change="handleChange()">
        <option value="social">Interes social</option>
        <option value="3">Estrato 3</option>
        <option value="4">Estrato 4</option>
      </select>

      <label for="tomas">Tomas</label>
      <input
        type="number"
        name="tomas"
        placeholder="Numero de Tomas"
        v-model="tomas"
      />

      <label for="luces">Luces</label>
      <input
        type="number"
        name="luces"
        placeholder="Numero de luces"
        v-model="luces"
      />

      <label for="interruptores">Interruptores</label>
      <input
        type="number"
        name="interruptores"
        placeholder="Numero de interruptores "
        v-model="interruptores"
      />

      <label for="interruptores">Precio unitario de tomas</label>
      <input
        type="number"
        name="interruptores"
        placeholder="Precio unitario"
        v-model="precioTomas"
      />

      <label for="interruptores">Precio unitario de luces</label>
      <input
        type="number"
        name="interruptores"
        placeholder="Precio unitario"
        v-model="precioLuces"
      />

      <label for="interruptores">Precio unitario de interruptores</label>
      <input
        type="number"
        name="interruptores"
        placeholder="Precio unitario"
        v-model="precioInterruptores"
      />

      <input class="btn" type="submit" value="Calcular Precio" />
    </form>

    <div class="recibo-container">
      <div class="recibo-header">
        <h2>Presupuesto</h2>
      </div>
      <div class="recibo-content">
        <h4>Nombre: {{ response.nombreEmpresa }}</h4>
        <h4>Nit: {{ response.nit }}</h4>
        <hr />
        <h4>Tomas: {{ response.tomaCant }}</h4>
        <h4>Luces: {{ response.cantidadLuces }}</h4>
        <h4>Interruptores: {{ response.cantidadInterruptores }}</h4>
        <div class="total">
          <p>Total:</p>
          <h3>{{ response.total }}$</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      nombre: "",
      nit: null,
      direccion: "",
      tipo: null,
      tomas: null,
      luces: null,
      interruptores: null,
      precioTomas: null,
      precioLuces: null,
      precioInterruptores: null,
      response: {
        nombre: "",
        nit: "",
        direccion: "",
        tipo: "",
        tomas: "",
        luces: "",
        interruptores: "",
        precioTomas: "",
        precioLuces: "",
        precioInterruptores: "",
        total: "",
      },
    };
  },

  methods: {
    async handleSubmit() {
      console.log(this.tomas);

      const url = "https://presupuesto-api.herokuapp.com/presupuesto";

      try {
        const response = await axios.post(url, {
          nombreEmpresa: this.nombre,
          nit: this.nit,
          tomaCant: this.tomas,
          puToma: this.precioTomas,
          cantidadLuces: this.luces,
          puLuces: this.precioLuces,
          puInterruptores: this.precioInterruptores,
          cantidadInterruptores: this.interruptores,
          tipoVivienda: this.tipo,
        });
        console.log(response.data.presupuesto);
        this.response = response.data.presupuesto;
      } catch (error) {
        console.error(error);
      }
    },

    handleChange() {
      if (this.tipo === "social") {
        this.tomas = 12;
        this.luces = 6;
        this.interruptores = 6;
      } else {
        this.tomas = null;
        this.luces = null;
        this.interruptores = null;
      }
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  position: relative;
  padding: 20px;
  bottom: 80px;
  height: 100%;
  background-color: #e1e1e1;
  /* justify-content: center; */
  align-items: center;
  width: 100%;
}
.form,
.recibo-container {
  display: flex;
  flex-direction: column;
  width: 40%;
  padding: 30px;
  text-align: left;
  background: white;

  -webkit-box-shadow: 4px 3px 10px -1px rgba(0, 0, 0, 0.76);
  box-shadow: 4px 3px 10px -1px rgba(0, 0, 0, 0.76);
}

input {
  height: 20px;
  margin-top: 10px;
  margin-bottom: 20px;
}

select {
  height: 30px;
  margin-top: 10px;
  margin-bottom: 20px;
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

.recibo-container {
  padding: 0;
}

.recibo-header {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #334979;
  color: white;
}

.recibo-content {
  padding-inline: 20px;
  padding-bottom: 20px;
}

.total {
  margin: 0 auto;
  width: 60%;
  height: auto;
  text-align: center;
  border: solid 1px #334979;
}
</style>
