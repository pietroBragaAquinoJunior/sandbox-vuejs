<script lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import CounterNumber from './components/CounterNumber.vue'
import CharacterList from './components/CharacterList.vue'
import ComputerLife from './components/ComputerLife.vue'
import PropsExample from './components/PropsExample.vue'
import PropsFunction from './components/PropsFunction.vue'
import ComputedProps from './components/ComputedProps.vue'
import EmitExample from './components/EmitExample.vue'
import EmitExample2 from './components/EmitExample2.vue'
import EmitExample3 from './components/EmitExample3.vue'
import SlotExample from './components/SlotExample.vue'
import SlotWithName from './components/SlotWithName.vue'
import FetchData from './components/FetchData.vue'
import UserPage from './components/UserPage.vue'
import SuspenseFetch from './components/SuspenseFetch.vue'
import RefComputeComposition from './components/RefComputeComposition.vue'
import CompPropEmitOthers from './components/CompPropEmitOthers.vue'

export default {
  components: {
    CounterNumber,
    CharacterList,
    ComputerLife,
    PropsExample,
    PropsFunction,
    ComputedProps,
    EmitExample,
    EmitExample2,
    EmitExample3,
    SlotExample,
    SlotWithName,
    FetchData,
    UserPage,
    SuspenseFetch,
    RefComputeComposition,
    CompPropEmitOthers
  },
  data() {
    return {
      contador: 0,

      nome: 'pietro',
      profissao: 'engenheiro',
      cep: '65070610',

      nomeAluno: 'pietrinho estudante',

      lista: [],
      resultadoAlerta: ''
    }
  },
  methods: {
    incrementarContador() {
      this.contador = this.contador + 1
    },
    mudarNomeAluno() {
      this.nomeAluno = 'Valadão Estudante'
    },
    consoleLog() {
      console.log('emit chamado')
    },
    adicionarPersonagemNaLista(personagem: any) {
      this.lista.push(personagem)
    },
    receberEmit() {
      this.resultadoAlerta = 'emit recebido'
    }
  },
  computed: {
    usuarioRefinado() {
      return {
        nome: this.nome,
        profissao: this.profissao
      }
    }
  }
}
</script>

<template>
  <header></header>
  <main>
    <CounterNumber />
    <CharacterList />
    <ComputerLife />
    <PropsExample :mensagem="'Olá'" />
    <p>{{ contador }}</p>
    <PropsFunction :incrementarContadorDoComponentePai="incrementarContador" />
    <ComputedProps :usuario="usuarioRefinado" />
    <p>{{ nomeAluno }}</p>
    <EmitExample @change-name="mudarNomeAluno" />
    <EmitExample2 @teste="consoleLog" />
    <ul v-for="(personagem, index) in lista" :key="`personagem.name-${index}`">
      <li>{{ personagem.name }}</li>
    </ul>
    <br/>
    <EmitExample3 @adicionar-personagem-lista="adicionarPersonagemNaLista" />
    <SlotExample>
      Olá, eu sou um butão!
    </SlotExample>
    <SlotWithName>
      <template v-slot:main>MAIN</template>
      <template v-slot:footer>FOOTER</template>
    </SlotWithName>
    <FetchData />
     O MELHOR LUGAR PARA COMEÇAR O FETCH É EM CREATED.
     BEFORE CREATED NÃO EXISTE NEM OS MÉTODOS, NEM O DATA.
     <hr/>
     <UserPage/>
     <hr/>
     <Suspense>
        <SuspenseFetch />
        <template #fallback>
           Esperando o fetch...
        </template>
     </Suspense> -->
    <!-- <Suspense>
        <RefComputeComposition/>
        <template v-slot:fallback></template>
     </Suspense> -->
    <CompPropEmitOthers @alerta="receberEmit" message="minha prop!" />
    <p>{{ resultadoAlerta }}</p>
  </main>

  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
