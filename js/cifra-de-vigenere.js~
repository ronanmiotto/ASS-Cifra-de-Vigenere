/*CIFRA DE VIGENÈRE*/



//O livro da natureza está escrito em caracteres matemáticos
/"use strict";
function encriptar(bool) {
	if (document.getElementById("chave").value.length == 0) {
		alert("Chave Vazia");
		return;
	}
	var chave = filterKey(document.getElementById("chave").value);
	if (chave.length == 0) {
		alert("Chave inválida!");
		return;
	}
	if (bool) {
		for (var i = 0; i < chave.length; i++)
			chave[i] = (26 - chave[i]) % 26;
	}
	var textElem = document.getElementById("texto");
	textElem.value = cripto(textElem.value, chave);
}

function cripto(entrada, chave) {
	var saida = "";
	for (var i = 0, j = 0; i < entrada.length; i++) {
		var c = entrada.charCodeAt(i);
		if (isUppercase(c)) {
			saida += String.fromCharCode((c - 65 + chave[j % chave.length]) % 26 + 65);
			j++;
		} else if (isLowercase(c)) {
			saida += String.fromCharCode((c - 97 + chave[j % chave.length]) % 26 + 97);
			j++;
		} else {
			saida += entrada.charAt(i);
		}
	}
	return saida;
}


function filterKey(key) {
	var result = [];
	for (var i = 0; i < key.length; i++) {
		var c = key.charCodeAt(i);
		if (isLetter(c))
			result.push((c - 65) % 32);
	}
	return result;
}

function isLetter(c) {
	return isUppercase(c) || isLowercase(c);
}

function isUppercase(c) {
	return c >= 65 && c <= 90;  
}

function isLowercase(c) {
	return c >= 97 && c <= 122;  
}

