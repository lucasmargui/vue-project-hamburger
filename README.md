<H1 align="center">Hamburger Project</H1>
<p align="center">🚀 Burger creation project using Vue for future references</p>

## Requirements
- Vue
- Vue Router


<div align="center">
 <h2> Create </h2>

 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/94ddc0ea-6359-453d-b154-fdb565880281" style="width:90%">
</div>

<div align="center">
 <h2> Orders </h2>

 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/0d3fb8bd-8d3f-46d3-b01e-2361ee4da467" style="width:90%">
</div>


## Simulating an API


### Database creation

<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/2c376844-b415-4ae3-a38d-9c483236568f" style="width:50%">
</div>
<br>

### Starting the json server

```
npx json-server --watch db/db.json
```

### Starting the project

```
npm run serves
```

## Project


## Create

Data Insertion Process into the Database Using the BurgerForm Component

The BurgerForm component is responsible for the data insertion logic into the database.

When the BurgerForm is loaded, the 'mounted' lifecycle is triggered, triggering the execution of an asynchronous function called 'this.getIngredients'. This function makes a request to the JSON server to obtain the ingredients through the fetch method. After receiving a JSON object containing the ingredients, it assigns this data to the variables declared in the Vue.js 'data()' method. Because they are reactive, changes to these variables cause Vue to rebuild the components or elements that use this data, as is the case with the 'select' that contains the ingredients.

<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/11f74578-2e07-4f4d-9eea-f6129d5bf91a" style="width:50%">
</div>
<br>

The data provided in the form inputs is linked to the variables defined in the "data()" method using the v:model directive.


<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/82d1e2b0-8c69-4741-ae2a-0c098e14dd03" style="width:45%">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/9fade0d2-3175-443d-826d-a270ef635581" style="width:45%">
</div>
<br>

When a form is filled out and the submit button is clicked, a custom function called "createBurger" is activated.

```
 <form id="burger-form" method="POST" @submit="createBurger">
```
<br>

In the following code, the "e.preventDefault()" function is used to prevent the form from being sent via the POST method, avoiding data loss when updating the page. The input values ​​are captured and stored in an object called "data". This object is then converted to a JSON string using the JSON.stringify(data) method. Subsequently, a POST request is made to the previously created JSON server, in which the JSON object is added to the database.

<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/eb171c22-408b-4255-a5cd-e3f7f32e8860" style="width:70%">
</div>


## Read

Process of reading data in the Database Through the DashBoard Component

When the BurgerForm is loaded, the 'mounted' lifecycle is triggered, triggering the execution of an asynchronous function called 'this.getPedidos'. This function makes a request to the JSON server to obtain requests using the fetch method. After receiving a JSON object containing the requests, it assigns this data to the variables declared in the Vue.js 'data()' method. Because they are reactive, changes to these variables cause Vue to rebuild the components or elements that use this data, such as updating the list. When finished, the 'this.getStatus' function is invoked, representing a simulated tabular structure in which the request identifiers are recorded along with their respective states.

<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/627140a4-05c4-495a-9c92-ebdf974905ad" style="width:90%">
</div>


## Update

- const option = event.target.value; : Here, the function extracts the selected value from the event event

- const dataJson = JSON.stringify({status: option});: The selected value is then converted into JSON format and placed inside an object with the key "status". This JSON object is converted to a string using JSON.stringify().

- const req = await fetch(http://localhost:3000/burgers/${id} : The fetch() function is used to make a PATCH request to the local server, where the burger update resource is located. URL is constructed based on the provided ID. The ${id} is replaced by the value of the id parameter passed to the function.

- const res = await req.json(): Once the request is completed, the result is extracted from the response using the json() method, which converts the response data into a JavaScript object.


<div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/dff8e24d-1f6d-411e-b66a-9f218899847e" style="width:90%">
</div>


## Delete


- Inside the function, there is a call to fetch, which is a native browser API for making HTTP requests. This call sends a DELETE request to the http://localhost:3000/burgers/${id} endpoint. The ${id} is replaced by the value of the id parameter passed to the function. This DELETE request is to remove a resource (in this case, a "hamburger") from the server.

 - After sending the DELETE request, the function waits for the response using await and converts it to JSON using req.json().

- The result of the conversion to JSON is stored in the res variable.

- After obtaining the response from the server and converting it to JSON, the function calls this.getPedidos(). Presumably, getPedidos() is a function that re-fetches orders (or related resources) after removing the hamburger, thus updating the user interface or application state with the updated data.


 <div align="center">
 <img src="https://github.com/lucasmargui/Vue_Projeto_Hamburgueria/assets/157809964/d2a62472-7510-4af1-94f0-afb4fcb18ff0" style="width:90%">
</div>

























