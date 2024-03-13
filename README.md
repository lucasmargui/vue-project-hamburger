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














