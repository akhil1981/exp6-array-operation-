<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Array Operations</title>

<style>

body {

font-family: Arial, sans-serif;

margin: 20px;

}

.form-section {

margin-bottom: 20px;

}

</style>

</head>

<body>

<h1>Array Operations</h1>

<div class="form-section">

<label for="arrayElement">Enter an element to add to the array: </label>

<input type="text" id="arrayElement" placeholder="Enter element">

<button onclick="addElement()">Add Element</button>

<p><strong>Array:</strong> <span id="arrayDisplay">[]</span></p>

</div>

<div class="form-section">

<h3>Remove Specific Element</h3>

<label for="removeElement">Element to remove: </label>

<input type="text" id="removeElement" placeholder="Enter element to remove">

<button onclick="removeElement()">Remove</button>

</div>

<div class="form-section">
<h3>Check If Element Exists</h3>

<label for="checkElement">Element to check: </label>

<input type="text" id="checkElement" placeholder="Enter element to check">

<button onclick="checkElement()">Check</button>

<p id="checkResult"></p>

</div>

<div class="form-section">

<h3>Empty the Array</h3>

<button onclick="emptyArray()">Empty Array</button>

</div>

<!-- Link to JavaScript file -->

<script> let array = []; 

function addElement() {

const element = document.getElementById('arrayElement').value;

if (element) {

array.push(element);

displayArray();

document.getElementById('arrayElement').value = '';

}

}

function displayArray() {

document.getElementById('arrayDisplay').innerText = JSON.stringify(array);

}

function removeElement() {

const elementToRemove = document.getElementById('removeElement').value;

array = array.filter(item => item !== elementToRemove);

displayArray();

document.getElementById('removeElement').value = ''; 

}

function checkElement() {

const elementToCheck = document.getElementById('checkElement').value;

const exists = array.includes(elementToCheck);

const resultText = exists ? `"${elementToCheck}" is in the array.` : `"${elementToCheck}" is 

NOT in the array.`;

document.getElementById('checkResult').innerText = resultText;
}

function emptyArray() {

array = [];

displayArray();

document.getElementById('checkResult').innerText = ''; 

}

</script>

</body>

</html>
