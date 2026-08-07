# Anotações Técnicas
> Este arquivo reúne anotações, resumos e testes que fiz ao longo da minha jornada de aprendizado em programação — API, ESLint, Azure, React, React Native, Vue, Javascript e outros tópicos.
>
> Como foram muitos conteúdos lidos, resumidos e testados podem haver divergências nos conteúdos aqui descritos com o que talvez você conheça, assim peço a gentileza de me enviar sugestões de correções ou adição de conteúdo e texto.
>
> O objetivo deste documento é poder ajudar outras pessoas que também estão no mundo da programação e precisam de algo um pouco mais detalhado e objetivo.
>
> Este conteúdo estava originalmente no README principal do repositório; foi movido para cá para que o README possa funcionar como um índice dos projetos.

## Sumario 
* [API](#api)
* [ESLINT](#eslint)
* [Azure](#azure)
* [GIT (Em breve)]
* [Javascript](#javascript)
* [PHP](#php)
* [NodeJS (Em breve)]
* [React](#react)
* [React Native](#react-native)
* [HTML5 (Em breve)]
* [CSS3 (Em breve)]
* [SASS (Em breve)]
* [Programação Funcional (Em breve)]
* [Pattern Strategy (Em breve)]
* [Pattern MVC (Em breve)]
* [Pattern Factory (Em breve)]
* [Pattern Sigleton (Em breve)]
* [Atomic Design (Em breve)]
* [Webpack (Em breve)]
* [Axios (Em breve)]
* [JWT (Em breve)]
* [Vue](#vue)
  * [Lifecycle Hooks](#lifecycle-hooks)
  * [Transferência de dados entre componentes](#transferência-de-dados-entre-componentes)
* [Quasar](#quasar)
* [Laravel](#laravel)
* [Mysql (Em breve)]
* [Node](#node)
* [MongoDB (Em breve)]
* [Mongoose (Em breve)]
* [Deno](#deno)
* [CORS (Em breve)]
* [Links](#links)

## API 
É um conjunto de rotinas e padrões de programação para acesso a um aplicativo baseado na Web.

Responsavel por estabelecer a comunicação entre diferentes serviços, assim pode-se criar e comunicar com várias outras aplicações  sem a necessidade principal de construir novas API's ou novas estruturas de back-end.

**Endpoint:** O conceito de ENDPOINT dentro de Web Services é a URL onde seu serviço pode ser acessado por uma aplicação cliente, em outros casos pode ser considerado como **algo que está nas pontas**, como no caso do par de cada ponta da conexão TCP.

### REST -> REpresentational State Transfer(Transferencia de Estado Representativo)
A transferencia de dados é feita de uma maneira **simbólica**, **figurativa**, **representativa**, de maneira didática.
A transferencia de dados é geralmente usando protocolo **HTTP**.

**Resource:** É a abstração sobre um determinado tipo de informação que uma aplicação gerencia, para que se aplique ao padrão REST __cada recurso precisa ter uma identificação única__ exemplo: __http://URI/RESOURCE_NAME/INFO__

### RESTFul
É a aplicação de todos os padrões REST na API.

### Padrões para ser RESTFul 

- Cliente separado do Servidor: Separação do cliente e do servidor, dessa forma, podemos ter uma portabilidade do sistema;
- Stateless (Sem estado): Cada requisição que o cliente faz para o servidor, deverá conter todas as informações necessárias para o servidor entender e responder a requisição, Exemplo: a sessao do usuario devera ser enviada em todas as requisições para saber se aquele usuario esta autenticado e apto a usar os serviços, o servidor não pode armazenar que o cliente foi autenticado antes;
- Cacheable: As respostas para uma  requisição deverão ser explicitas ao dizer se aquela requisição pode ou não ser cacheada pelo cliente;
- Layered System (Sistema em camadas): o cliente acessa a um endpoint sem precisar saber da complexidade de quais passos estão sendo necessários para o servidor responder a requisição, ou quais outras camadas o servidor estará lidando para que seja respondido;
- Code on Demand (Opcional): Da a possibilidade da nossa aplicação pegar codigos como javascript no lado do cliente;
- Uniform Interface (Interfacec uniforme): Manter o padrão na construção da API, consistente, constante, padrão ou coerente.

### Verbos HTTP
Existem diversos porém os mais utilizados são:
- GET: Buscar dados, pode ser usado com parâmetros;
- POST: Enviar dados ou informações para serem processadas, utiliza-se de um corpo (body);
- PUT: Atualizar dados, com um parâmetro de identificação obrigatório e um corpo com novos dados, no caso de usar este verbo indica-se que **envie no corpo todos os dados** independente de qual de fato foi alterado, para enviar apenas um dado alteardo por convenção utilizar o verbo PATCH;
- PATCH: Usado para editar o recurso sem a necessidade de enviar todos os atributos, com um parâmetro de indicação obrigatório;
- DELETE: Deletar, remover ou apagar dados, com um parâmetro de identificação obrigatório.

### Boas Práticas na criação de API's
- Utlizar verbos HTTP adequados para as requisições;
- Não utilizar barras no final da recursos;
- Use o mesmo padrão de URI na identificação dos recursos;
- Nunca deixe o cliente sem resposta;
- Na construcao da chave secreta do token usar o mesmo numero de bits do token.

### Status das respostas
- 1xx: Informação
- 2xx: Sucesso
    - 200: OK
    - 201: CREATED
    - 204: NOT CONTENT (PUT POST DELETE)
- 3xx: Redirection
- 4xx: Client Error
    - 400: Bad Request
    - 404: Not Fund:
- 5xx: Server Error
    - 500: Internal Server Error

## ESLINT  
Comandos úteis:
- eslint --init: Inicia uma configuração, respondendo as perguntas, ao finalizar gera um arquivo .eslintrc||.json||.js||.yaml
- eslint [file.js]: Efetua a verificação do arquivo e mostra um log com os erros no formato [line]:[column] error [message]
- eslint --fix [file.js]: Executa a correção dos erros que forem encontrados

## Azure 
Armazenar informações uteis acerca da utilização do AZURE e de como construir e fazer o deploy de uma API.

### 3.1 Estrutura base para a API for Azure (AFA - API For Azure)
Existem diversas maneiras de fazer o deploy de uma aplicação para o AZURE vou descrever apenas 1:

- Deploy via GIT, VSCode ou CLI: 
    - Ao realizar o deploy por alguns destes modelos o AZURE vai buscar pelos arquivos de iniciailização do projeto: app.js, server.js ou comando no package.json na raiz do projeto.
- É obrigatório o uso do .gitignore;
- No arquivo de inicialização: Manter o host como automático ou remove-lo da configuração e manter a porta como: process.env.PORT || [LOCAL_PORT]
- O arquivo process.json faz parte da orquestracao do PM2 e pode ser opcional.

## PHP

## React
Toda vez que for embutir javascript dentro do html pelo JSX precisa usar chaves sem aspas.

A sintax **<>html</>** é chamada de fragment, permite criar as divs invisiveis para poder utilizar múltiplos componentes ou tags html dentro de um mesmo componente, essa técnica ajuda quando você não precisa aninhar diversas divs ou esta trabalhando com componentização (quando separa as camadas em componentes).

Ao executar uma funcao de repeticao (map, forEach e etc) precisa inserir a propriedade [key] dentro do elemento html pai:
ex: 
```
    <tr key='indice'>
        map(func())
    </tr>
```
Cada componente do React recebe como parametro um objeto chamado __props__, quando instalamos outras bibliotécas, alguns de seus métodos são acessados através deste parametro, como é o caso da bibliotéca __react-router-dom__, você pode usar a desestruturação para pegar apenas as propiedades que for usar, como exemplo:
Para usar navegacao usamos o __history__ ou __location__, ambas propriedades da bibliotéca __react-router-dom__: 
```
    import React from 'react'
    export default function App({history, location}){
        console.log(history)
        console.log(location)

        return (<h1>Hello World!</h1>)
    }
```
Alguns métodos do history:
```
    history.push('/uri'): Redireciona o usuário
```
Um stateless componente tem a seguinte sintax:
```
export default () => ( jsx )
```

### 9.1 Ferramentas:
**State:**
Para trabalhar com state react:
```
    import React, {useState} from 'react'
    export default function App(){
        const [var, setVar] = useState(valorInicial)

        return (<h1>Hello World</h1>)
    }
```
Funciona parecido com um get and set, o valor inicial pode ser um array vazio, uma string vazia, um valor boolean dentre outros.

**Effect:**
O useEffect é um método que pode executar blocos de códigos antes renderizar o componente, para seu uso considere:
```
    import React, {useEffect} from 'react'
    export default function App(){
        useEffect(function(){
            console.log('Effect em funcionamento!')
        },[])

        return (<h1>Hello World!</h1>)
    }
```
Ao declarar o useEffect com a dependencia vazia ele executa apenas uma vez, se você precisa que execute o mesmo bloco de código baseado em alguma dependencia, inserir esta no array de dependências.

Sintax: useEffect(func(), [array de dependencias]), 

**React Router Dom:**
A biblioteca react-router-dom permite criar rotas dentro de uma aplicação React.
O componente __Switch__ restring a executar apenas uma rota por vez, evitando assim que por acidente a aplicação tente renderizar 2 rotas ao mesmo tempo.

A propriedade __exact__ dentro de __Route__ configura a rota para acessar apenas o valor da __uri__ exatamente igual ao definido em __path__

## React Native
Muitos dos conceitos utilizados no React JS você pode utilizar aqui no React Native.

Aplicativos moveis usam o conceito de densidade de pixel, usar sempre 3 tamanhos de logo com quantidade de pixels diferentes superiores.

Cada componente precisa ter estilizacao propria.

Todas os componentes __View__ criadas ja possuem [display:'flex'] e [flexDirection:'column'] e todos os componentes de texto precisam ser estilizados.

O React Native, diferentemente do React JS, não utiliza tags html ele é totalmente baseado em componentes, o estilo continua sendo css porém para definição dos estilos usa-se o componente __StyleSheet__ nativo do React Native, abaixo um exemplo:
```
    import {StyleSheet} from 'react-natvie'

    const styles = StyleSheet.create({
        className: {
            ...styles
        }
    })    
```
**Obs:**
As propriedades nao possuem hifens [-], diferentemente de arquivos.css, e os valores sao atribuidos usando aspas simples [''].
Para usar os estilos precisa definir a propriedade __style__ dentro de cada componente:
```
    import React from 'react'
    import {View, StyleSheet} from 'react-native'

    export default function App(){

        return (
            <View style={styles.estilo}>
                <Text>Hello World</Text>
            </View>
        )
    }
```
Você também pode querer utilizar dois estilos dentro de um mesmo componente, para isto basta usar um array para chamar os estilos:
```
    import React from 'react'
    import {View, StyleSheet} from 'react-native'

    export default function App(){

        return (
            <View style={[styles.estilo1, styles.estilo2]}>
                <Text>Hello World</Text>
            </View>
        )
    }
```

### 10.1 Componentes
* Text 
    * Pode colocar texto:
    ```
        import React from 'react'
        import {Text} from 'react-native'

        export default function App(){

            return (
                <Text>Hello World</Text>            
            )
        }
    ```
* View:
    * Container visual, funciona como se fosse uma div, você não pode adicionar textos sem usar o componente text:
    ```
        import React from 'react'
        import {View, Text} from 'react-native'

        export default function App(){

            return (
                <View>
                    <Text>Hello World</Text>       
                </View>            
            )
        }
    ```
* KeyboardAvoidingView:
    * Usado para que a __View__ se desloque ao abrir o teclado, usado apenas para o IOS, no Android é uma ação padrão do sistema, ao declarar este componente precisa definir a propriedade behavior="padding", você pode também definir uma propriedade com condicional para habilitar este componente apenas em dispositivos com IOS:
    ```
        import React from 'react'
        import {KeyboardAvoidingView} from 'react-native'

        export default function App(){

            return (
                <KeyboardAvoidingView enabled={Platform.OS === 'ios'} behavior="padding" >
                    <Text>Hello World</Text>       
                </KeyboardAvoidingView>            
            )
        }
    ```
* AsyncStorage 
    * Método que armazena dados direto no dispositivo, é asincrono, por tanto precisa utilizar async/await ou .then.catch ao utilizar:
    ```
        import React, {useEffect} from 'react'
        import {AsyncStorage} from 'react-native'

        export default function App(){
            useEffect(()=>{
                setItem()

                AsyncStorage.getItem('user').then(resolve=>{
                    console.log(resolve)
                })
            })

            async function setItem(){
                AsyncStorage.setItem('key', 'value')
            }

            return (
                <View>
                    <Text>Hello World</Text>       
                </View>            
            )
        }
    ```

Para usar redirecionamento e navegacao usar o a propriedade do objeto { navigation } = navigation.navigate('NomeRota')
- SafeAreaView
  Cria uma box/view na parte segura de visualizacao dos dispositivo

Para buscar itens e montar em forma de lista ou padrao de sequencia e bom criar um componente para isto
Componentes que nao sao paginas nao tem acesso a propriedade [navigation] por padrao para contornar isto usar a lib [withNavigation] do [react-navigation] que adiciona a propriedade navigation a qualuqer componente que n seja pagina, basta envolver a funcao/componente no metodo [withNavigation(funcname)]

Para usar dois estilos em um elemento usar array [style1, styleN]

###### Erros Comuns:
**Erro da extensão intl:** Este erro ocorreu comigo quando fui instalar o Codigniter 4, assim que iniciou a instalação apresentou o erro abaixo:

```
Problem 1
    - codeigniter4/framework v4.0.0-rc.3 requires ext-intl * -> the requested PHP extension intl is missing from your system.
    - codeigniter4/framework v4.0.0-rc.2.1 requires ext-intl * -> the requested PHP extension intl is missing from your system.
    - codeigniter4/framework v4.0.0-rc.2 requires ext-intl * -> the requested PHP extension intl is missing from your system.
    - codeigniter4/framework v4.0.0-rc.1 requires ext-intl * -> the requested PHP extension intl is missing from your system.
    - Installation request for codeigniter4/framework ^4@rc -> satisfiable by codeigniter4/framework[v4.0.0-rc.1, v4.0.0-rc.2, v4.0.0-rc.2.1, v4.0.0-rc.3].

  To enable extensions, verify that they are enabled in your .ini files:
    - C:\xampp\php\php.ini
  You can also run `php --ini` inside terminal to see which files are used by PHP in CLI mode.
```

**Solução:** Caso você esteja utilizando o XAMPP com a versão PHP 7, abra o php.ini e busque pelo trecho: extension=intl, caso esteja com ponto e virgula na frente (;extension=intl) remova, salve o arquivo e reinicie o servidor.

## Vue
>Vue (pronuncia-se /vjuː/, como view, em inglês) é um framework progressivo para a construção de interfaces de usuário. Ao contrário de outros frameworks monolíticos, Vue foi projetado desde sua concepção para ser adotável incrementalmente. A biblioteca principal é focada exclusivamente na camada visual (view layer), sendo fácil adotar e integrar com outras bibliotecas ou projetos existentes. Por outro lado, Vue também é perfeitamente capaz de dar poder a sofisticadas Single-Page Applications quando usado em conjunto com ferramentas modernas e bibliotecas de apoio. fonte: https://br.vuejs.org/v2/guide/index.html

Atualmente em sua versão 3 novas ferramentas foram surgindo para facilitar o desenvolvimento.

Algumas curiosidades: 
Na versão 2 ou anterior não é considerado uma boa prática usar o v-if junto de um bloco v-for:

**Bad**
```
    <div v-if="items.length" v-for="(item, i) in items">
        {{ item }}
    </div>
```
**Good**
```
    <div v-if="items.length">
        <div v-for="(item, i) in items">
            {{ item }}
        </div>
    </div>
```
O atributo HTML v-show é diferente do v-if, o v-if não registra o elemento html caso seja false, ou seja, não aparece no DOM enquanto o v-show apenas esconde, um tipico uso do v-show é na amostragem do menu sidebar.

Os atributos binds do Vue podem ser abreveados com os dois pontos (:), exemplo:

**Original**
```
    <div v-bind:attribute-name="value"></div>
```
**Abreviado**
```
    <div :attribute-name="value"></div>
```

Também funciona para os atributos de função (v-on), podem ser usados o arroba (@):
**Original**
```
    <div v-on:component-function="method"></div>
```
**Abreviado**
```
    <div @component-function="method"></div>
```
### Lifecycle Hooks
O Vue js possui hooks de ciclo de vida dos componentes assim como os outros frameworks, todos os hooks do Vue tem acesso a variavel **this** e por tanto não podem ser usados com _arrow functions_:

 - **beforeCreate**: Chamado imediatamente após instanciar o vue, não tem acesso a _computed properties_, _watchers_, _data_ e _methods_
 - **created**: Foi configurado: _observer data_, _computed properties_, _methods_, _watch/event callbacks_, ainda não tem acesso ao _DOM_ nem a propriedade **$el**.
 - **beforeMount**: A função _render_ está prestes a ser invocada pela primeira vez.
 - **mounted**: Invocado logo após a instância ter sido montada, onde **el** é substituído pelo recém criado **vm.$el**. Se a instância raiz é montada em um elemento já presente no documento, **vm.$el** também estará presente no documento quando mounted for invocada. Observe que o **mounted** não garante que todos os **componentes filhos** também já tenham sido montados. Se você quiser esperar até que toda a camada view do componente em questão tiver sido renderizada, você pode utilizar **vm.$nextTick** dentro do mounted.
 - **beforeUpdate**: Invocado quando os dados mudam, antes do virtual _DOM_ ser re-renderizado e atualizado. Este é um bom local para acessar DOM existente antes de uma atualização, por exemplo, para remover escutas de eventos adicionadas manualmente.
 - **updated**: Invocado após a mudança de dados fazer o virtual _DOM_ ser re-renderizado e atualizado. O _DOM_ do componente estará no estado updated quando este gatilho for invocado, assim você pode realizar operações dependentes de _DOM_ neste gatilho. Entretanto, na maioria dos casos você deveria evitar mudar o estado deste gatilho, melhor utilizar propriedades computadas ou observadores. Observe que o updated não garante que todos os componentes filhos também já tenham sido montados. Se você quiser esperar até que toda a camada view do componente em questão tiver sido renderizada, você pode utilizar **vm.$nextTick** dentro do **updated**.
 - **beforeDestroy**: Invocado logo antes da instância Vue ser destruída. Neste ponto a instância ainda é completamente funcional.
 - **destroy**: Invocado após a instância Vue ter sido destruída. Quando este gatilho é invocado, todas as diretivas da instância Vue já foram desvinculadas, todos os event listeners foram removidos, e todas as instâncias Vue filhas também foram destruídas.

 <!-- XXX TODO :: Sessão dos watchers e computed properties -->
 <!-- XXX TODO :: Sessão do v-model -->
 <!-- XXX TODO :: Sessão das diretivas -->
 <!-- XXX TODO :: Sessão do Vuex -->
 <!-- XXX TODO :: Sessão dos testes e QA -->
 <!-- XXX TODO :: Sessão do Vue 3 -->

### Transferência de dados entre componentes:
Para transferir dados entre componentes uso muito as props via atributos html com bind do vue a diretiva **v-on** (https://br.vuejs.org/v2/api/#v-on) e a função **$emit** dos métodos da instância (https://br.vuejs.org/v2/api/#vm-emit):

*componentePai.vue*
```
    <template>
        <h6>Bem vindo {{ name }}</h6>
        <componente-filho :prop1="msg" @input="onGetName"/>
    </template>

    <script>
    import componenteFilho from './componenteFilho'
    export default {
        components: {
            componenteFilho
        },
        data: () => ({
            name: '',
            msg: 'Estamos felizes em ver você!'
        }),
        methods: {
            onGetName (name) {
                this.name = name 
            }
        }
    }
    </script>

```
*componenteFilho.vue*
```
    <template>
        <p>{{ prop1 }}</p>
        <button @click="onSendName">Envie seu nome</button>
    </template>

    <script>

    export default {
        props: ['prop1'],
        methods: {
            onSendName () {
                this.$emit('input', 'Um Nome Qualquer')
            }
        }
    </script>

```
Assim você podem manter a reatividade das propriedades e a comunicação entre os componentes.

### Usando a diretiva v-slot
Os Slots do Vue são uma excelente forma de reaproveitar componentes ao longo do projeto, desta forma é possível fazer com que um componente tenha vários comportamentos dentro de um mesmo objetivo, mas atenção as boas práticas de construção de componentes para que não acumule responsabilidades demais a um unico componente, abaixo um exemplo de uso da diretiva v-slot do vue:

Um exemplo ilustrado de como reaproveitar um componente que envolve renderizar botões:
```
//App.vue

<template>
  <div id="app">
  <button-helper>
    <h1 slot="title">Lista de botões</h1>
    <button slot="red" type="button" class="Red">Red</button>
    <button slot="green" type="button" class="Green">Green</button>
    <button slot="blue" type="button" class="Blue">Blue</button>
  </button-helper>
  </div>
</template>
<script>
import buttonHelper from './components/Buttons.vue'
export default {
  name: 'App',
  components: {
    'button-helper':buttonHelper
  }
    }
</script>

<style>
.Red{
  width:120px;
  height: 50px;
  margin: 50px;
  padding: 10px;
  background-color:red;
  text-align: center;
  cursor:pointer;
}
.Green{
  width:120px;
  height: 50px;
  margin: 50px;
  padding: 10px;
  background-color:Green;
  text-align: center;
  cursor:pointer;
}
.Blue{
  width:120px;
  height: 50px;
  margin: 50px;
  padding: 10px;
  background-color:blue;
  text-align: center;
  cursor:pointer;
}
</style>
```
```
//Buttons.vue
<template>
<div>
  <h1>Esta é a lista de botoes do App.vue</h1>
<div>
  <slot name="title"></slot>
  <slot name="green"></slot>
</div>
<div>
  <slot name="title"></slot>
  <slot name="blue"></slot>
</div>
<div>
  <slot name="title"></slot>
  <slot name="red"></slot>
  </div>
<div>
  <slot name="title"></slot>
  <slot name="blue"></slot>
  <slot name="red"></slot>
  <slot name="green"></slot>
</div>
</div>
</template>
<script>
export default {
  name: 'Buttons',
    }
</script>
```

O exemplo acima vai renderizar um botão de cada cor na ordem (Verde, Azul e Vermelho) cada um com o titulo 'Lista de botões' muito parecido com o comportamento de um v-for.



## Javascript
Nesta seção vou abordar assuntos sobre o Javascript, Typescript e Ecmascript


### Operador de coalescência nula (Nullish Coalescing Operator :: ES11(2020))
Antes do lançamento do ES11 tinhamos apenas o operador lógico OR (||) que no exemplo: 
```
    const var1 = 1
    const var2 = 2

    console.log(var1 || var 2) // return var1

    const var3 = null
    const var4 = 2

    console.log(var3 || var 4) // return var4
```

Returna o valor cuja expressão retorne verdadeiro.

Mas em alguns casos queremos que a próxima expressão seja avaliada apenas quando a primeira for null ou undefined:

```
let result = undefined ?? "Hello";
console.log(result); // Hello

result = null ?? true; 
console.log(result); // true

result = false ?? true;
console.log(result); // false

result = 45 ?? true; 
console.log(result); // 45

result = "" ?? true; 
console.log(result); // ""

result = NaN ?? true; 
console.log(result); // NaN

result = 4 > 5 ?? true; 
console.log(result); // false because 4 > 5 evaluates to false

result = 4 < 5 ?? true;
console.log(result); // true because 4 < 5 evaluates to true

result = [1, 2, 3] ?? true;
console.log(result); // [1, 2, 3]

```
E isto é feito com o novo operador de coalescência nula, apenas avalia a próxima expressão quando a primeira for null ou undefined.

>fonte: https://www.freecodecamp.org/news/nullish-coalescing-operator-in-javascript/

## Links 
1. https://blog.caelum.com.br/rest-principios-e-boas-praticas/
2. https://github.com/mysqljs/mysql#introduction
3. https://eslint.org/
4. https://pt.stackoverflow.com/questions/86399/qual-a-diferen%C3%A7a-entre-endpoint-e-api
5. https://www.devmedia.com.br/servicos-restful-verbos-http/37103
6. https://www.pubnub.com/blog/realtime-geo-tracking-app-react-native/

###### Anotações em Geral
Para testar se esta conseguindo acessar a porta usar o link: portquiz.net:30000[porta_desejada]
