---
layout: default
title: Objects
group: basico
---

Até agora, para executar o seu código você tem usado o seguinte código:

	object Nome {
		// seu código
	}

Esse object nada mais é do que uma classe que Scala garante para você que existirá apenas uma instância dela na sua
aplicação. Por isso você não precisa instanciá-la. Scala já instancia para você.

Um dos grandes usos de `object`s é usá-la no lugar de strings mágicas, porque você não corre o risco de passar o valor 
errado.

Outro, você já conhece mas não sabia. Quando uma `case class` é compilada, ela gera um `object` especial que tem o mesmo
nome que ela (chamado de companion object). É com isso e um pouco mais de magia que você consegue instanciar uma
case class sem usar `new`.

## Exercícios

1. Crie alguns objects
2. Também existe o case object. Descubra o que ele faz.
