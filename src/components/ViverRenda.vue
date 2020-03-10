<template>
  <div>
    <h1>Calculadora Viver de Renda</h1>
    <p>Quanto eu preciso para alcancar minha liberdade financeira: </p>
    <div>
        <label>Quanto voce quer ganhar por mês? </label>
        <input v-model="ganhar" type="text" />
    </div>

    <div>
        <label>Qual o tipo de aplicacao: Renda Fixa - Tesouro Direto</label>
    </div>

    <hr />

    <div v-if="isDev" class="dividir-abas-outras-aplicacoes">
      
      <div>
          <label>Deposito Inicial: </label>
          <input type="text" />
      </div>

      <div>
          <label>Deposito Mensal: </label>
          <input type="text" />
      </div>


      <div>
          <label>Tempo de investimento: </label>
          <input type="text" />
      </div>

    </div>

    <button @click="calcular">Calcular</button>

    <p>Você precisará de R$: {{ formatPrice(resultado) }} investido.</p>


  </div>
</template>

<script>
export default {
  name: 'ViverRenda',
  props: {
    msg: String
  },
  data: function() {
      return {
          resultado: 3,
          ganhar: 0,
          isDev: false,
          tiposInvestimento: [
                { text: 'Tesouro Direto', value: '1' },
                { text: 'Fundos Imobiliarios', value: '2' },
            ]
      }
  },
  methods: {
      calcular(){
          this.resultado = this.ganhar / (0.4 / 100)
      },
      formatPrice(value) {
        let val = (value/1).toFixed(2).replace('.', ',')
        return val.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
