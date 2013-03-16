---
layout: default
title: Funções
group: basico
---

Funções são, basicamente, blocos de código que você pode passar para vários lugares.

Por exemplo:

	val a : (Int => String) = (x : Int) => {
		x.toString
	}

	a(123) // devolve "123"

* `Int => String` é o tipo de uma função que recebe um `Int` e devolve uma `String`
* `(listaDeParametros) => {seuCodigo}` é a declaração da função
* O tipo da variável `a` pode ser omitido
* Se o tipo da variável `a` não for omitido, você pode usar a notação curta de declaração de funções(o mesmo vale 
se ela for passada para métodos):
		val a : (Int => String) = _.toString
		// Nesse caso o _ será o primeiro parâmetro. Caso fossem dois os parâmetros, você 
		// poderia usar mais um _ para representar o segundo parâmetro.

## Exercícios:

1. Coloque algumas funções em `val`s. Utilize-as.
2. Crie métodos que recebem funções. Coloque os Tipos.
3. Crie métodos que devolvem funcões Coloque os Tipos.
4. Crie métodos que recebem e devolvem funções. Coloque os Tipos.
5. Tente passar um método compatível (que devolva e receba os mesmos tipos) para um lugar que espera uma 
função. O que acontece? Procure por **Eta Expansion**.

