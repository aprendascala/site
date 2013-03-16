---
layout: default
title: Variáveis e valores
group: basico
---

Scala separa variáveis (que podem ter seu valor modificado) e valores (que não podem ter seu valor modificado).

Para declarar uma variável:

	var nome = "Jonas"
	nome = "Outro nome"

Para declarar um valor:
	
	val nome = "Jonas"
	// nome = "Outro nome" não compila

Scala funciona muito melhor quando não mutamos o estado de nada, então é sempre aconselhável evitar o uso de variáveis,
usando valores em seus lugares.

Olhando os exemplos acima, você vai notar que não foi necessário dizer qual era o tipo da variável/valor. Isso acontece
porque Scala infere o tipo para você. Em alguns casos pode ser necessário (ou ficar mais fácil de entender) colocar o
tipo. Para isso, basta usar a notação:

	val nome:String = "Jonas"

Em Scala, ao contrário de Java e várias outras linguagens, o tipo vem após o identificador.

## Exercícios:

1. Declare alguns valores de vários tipos, como Int, String, Double, etc
2. Coloque tipos explícitos para essas variáveis
