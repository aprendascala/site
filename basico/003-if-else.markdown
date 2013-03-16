---
layout: default
title: If e Else
group: basico
---

A sintaxe de `if` e `else` é bem semelhante à de várias linguagens.

	if (condicaoBooleana) {
		// codigo quando verdadeiro
	} else {
		// codigo quando falso
	}

A principal diferença é que em Scala, quase todas as expressões devolvem um valor, incluindo `if`s.

	val resultado = if (1 > 0) "maior" else "menor"
	println(resultado) // imprime "maior"

## Possíveis problemas

1. Um problema comum usando `if`s é a seguinte espressão:

		val r = if (1 > 0) "maior"
		r.toBytes // Não compila dizendo que `Any` não tem o método toBytes 

	O código não compila porque todo `if` sempre tem um else. O código acima é equivalente à:

		val r = if (1 > 0) "maior" else () 
		// esse () é uma instância de `Unit`,que significa nada, lembram?

	Olhando para esse código, fica claro que a única inferência possível para o tipo do resultado da expressão seja
	o ancestral comum de `String` e `Unit`, que é o `Any` (equivalente ao Object de Java).

## Exercícios

1. Escreva alguns `if`s com e sem `else`.
2. Atribua o resultado de uam expressão `if/else` para uma variável
3. Passe para um método o resultado de uma expressão `if/else`
