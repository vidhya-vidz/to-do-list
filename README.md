<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="vieport" content="width=device-width, initial-scale=2.0">
	<link rel="stylesheet" href="style.css">
	<title>My To Do List</title>
</head>
<body>
	<h1>My To Do List</h1>
	<div class="container">
		<input id="inputField" type="text"><button id="addToDo">+</button>
		<div class="to-dos" id="toDoContainer">
		</div>
    </div>
    <script src="main.js"></script>
</body>
</html>

html, body{
	width: 70%;
	margin: 0 auto;
	font-family: Times New Roman;
}

.container {
	width: 380px;
}

#inputField {
	width: 320px;
	height: 48px;
	border: 5px darkred;
	outline-color: darkred;
	font-size: 28px;
	vertical-align: middle;
}

#addToDo{
	height: 55px;
	width: 55px;
	border: 2px darkblue;
	vertical-align: middle;
	font-size: 32px;
}

.to-dos{
	margin-top: 28px;
}

.paragraph-styling {
	margin: 0;
	cursor: pointer;
	font-size: 22px;
}

let addToDoButton = document.getElementById('addToDo');
let ToDoContainer = document.getElementById('toDoContainer');
let inputField = document.getElementById('inputField');

addToDoButton.addEventListener('click', function(){
	var paragraph = document.createElement('p')
	paragraph.classList.add('paragraph-styling');
	paragraph.innerText = inputField.value;
	ToDoContainer.appendChild(paragraph);
	inputField.value ="";
	paragraph.addEventListener('click', function(){
		paragraph.style.textDecoration = "line-through";
	})
	paragraph.addEventListener('dblclick', function(){
		ToDoContainer.removeChild(paragraph);
	})

})
