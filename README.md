<H1 align="center">Projeto Hamburgueria</H1>
<p align="center">🚀 Projeto de criação de hamburgueria utilizando Vue para referências futuras</p>

## Requisitos
- Vue
- Vue Router


## Simulando uma Api


### Criação do banco de dados

<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/2c376844-b415-4ae3-a38d-9c483236568f" style="width:50%">
</div>
<br>

### Iniciando o servidor json

```
npx json-server --watch db/db.json
```

## Projeto


## Create 

Processo de Inserção de Dados no Banco de Dados Através do Componente BurgerForm

O componente BurgerForm é responsável pela lógica de inserção de dados no banco de dados.

Quando o BurgerForm é carregado, o ciclo de vida 'mounted' é acionado, desencadeando a execução de uma função assíncrona chamada 'this.getIngredientes'. Esta função realiza uma requisição ao servidor JSON para obter os ingredientes por meio do método fetch. Após receber um objeto JSON contendo os ingredientes, atribui esses dados às variáveis declaradas no método 'data()' do Vue.js. Por serem reativas, as mudanças nessas variáveis fazem com que o Vue reconstrua os componentes ou elementos que utilizam esses dados, como é o caso do 'select' que contém os ingredientes.

<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/11f74578-2e07-4f4d-9eea-f6129d5bf91a" style="width:50%">
</div>
<br>

Os dados fornecidos nos inputs do formulário são vinculados às variáveis definidas no método "data()" utilizando a diretiva v:model.


<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/82d1e2b0-8c69-4741-ae2a-0c098e14dd03" style="width:45%">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/9fade0d2-3175-443d-826d-a270ef635581" style="width:45%">
</div>
<br>

Quando um formulário é preenchido e o botão de envio é clicado, uma função personalizada chamada "createBurger" é ativada.

```
 <form id="burger-form" method="POST" @submit="createBurger">
```
<br>

No código a seguir, a função "e.preventDefault()" é utilizada para impedir o envio do formulário via método POST, evitando a perda de dados ao atualizar a página. Os valores dos inputs são capturados e armazenados em um objeto chamado "data". Em seguida, esse objeto é convertido em uma string JSON através do método JSON.stringify(data). Posteriormente, é feita uma requisição POST para o servidor JSON previamente criado, na qual o objeto JSON é adicionado ao banco de dados.

<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/eb171c22-408b-4255-a5cd-e3f7f32e8860" style="width:70%">
</div>


## Read

Processo de leitura de dados no Banco de Dados Através do Componente DashBoard

Quando o BurgerForm é carregado, o ciclo de vida 'mounted' é acionado, desencadeando a execução de uma função assíncrona chamada 'this.getPedidos'. Esta função realiza uma requisição ao servidor JSON para obter os pedidos por meio do método fetch. Após receber um objeto JSON contendo os pedidos, atribui esses dados às variáveis declaradas no método 'data()' do Vue.js. Por serem reativas, as mudanças nessas variáveis fazem com que o Vue reconstrua os componentes ou elementos que utilizam esses dados, como atualização da lista. Ao término, a função 'this.getStatus' é invocada, representando uma estrutura tabular simulada na qual são registrados os identificadores dos pedidos juntamente com seus respectivos estados.

<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/627140a4-05c4-495a-9c92-ebdf974905ad" style="width:90%">
</div>


## Update

- const option = event.target.value; : Aqui, a função extrai o valor selecionado do evento event

- const dataJson = JSON.stringify({status: option});: O valor selecionado é então convertido em formato JSON e colocado dentro de um objeto com a chave "status". Este objeto JSON é convertido em uma string usando JSON.stringify().

- const req = await fetch(http://localhost:3000/burgers/${id} : A função fetch()é usada para fazer uma requisição PATCH para o servidor local, onde o recurso de atualização de hambúrgueres está localizado. A URL é construída com base no ID fornecido. O ${id} é substituído pelo valor do parâmetro id passado para a função.

- const res = await req.json(): Uma vez que a requisição é completada, o resultado é extraído da resposta (response) usando o método json(), que converte os dados da resposta em um objeto JavaScript.


<div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/dff8e24d-1f6d-411e-b66a-9f218899847e" style="width:90%">
</div>


## Delete


- Dentro da função, há uma chamada para fetch, que é uma API nativa do navegador para fazer requisições HTTP. Essa chamada envia uma requisição DELETE para o endpoint http://localhost:3000/burgers/${id}. O ${id} é substituído pelo valor do parâmetro id passado para a função. Essa requisição DELETE é para remover um recurso (nesse caso, um "hambúrguer") do servidor.

 - Após o envio da requisição DELETE, a função aguarda a resposta usando await e a converte para JSON usando req.json().

- O resultado da conversão para JSON é armazenado na variável res.

- Após obter a resposta do servidor e converter para JSON, a função chama this.getPedidos(). Presumivelmente, getPedidos() é uma função que busca novamente os pedidos (ou recursos relacionados) após a remoção do hambúrguer, atualizando assim a interface do usuário ou o estado da aplicação com os dados atualizados.


  <div align="center">
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/d2a62472-7510-4af1-94f0-afb4fcb18ff0" style="width:90%">
</div>



## Resultado 

<div align="center">
  <h2> Criação de Hambúrguer </h2>
 
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/94ddc0ea-6359-453d-b154-fdb565880281" style="width:90%">
</div>

<div align="center">
  <h2> Pedidos </h2>
 
  <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/0d3fb8bd-8d3f-46d3-b01e-2361ee4da467" style="width:90%">
</div>


























