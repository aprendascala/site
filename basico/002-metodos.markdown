---
layout: default
title: Métodos
permalink: /basico/metodos.html
group: basico
---

Para definir um método em Scala é bem simples:

	def nomeDoMetodo(param1:Tipo1, param2:Tipo2):TipoRetorno = {
		// código do método
	}

E ele pode ser definido dentro de um `object`.

A maior parte das vezes não é necessário especificar o tipo de retorno. Uma exceção são os métodos recursivos,
que o compilador não consegue inferir o tipo de retorno.

Em Scala, a maior parte do tempo também não precisamos utilizar a palavra reservada `return`, porque a última 
expressão avaliada é devolvida para quem chamou o método.

	def devolveDois() = { 2 }

é um método válido.

## Possíveis problemas:

1. Um erro comum é esquecer do `=` antes do `{` na declaração do método. Quando você faz isso, o **TipoRetorno**
será `Unit`, que é semelhante ao `void` do Java (um tipo que significa "nada" ou "vazio".

## Exercícios:

1. Declare alguns métodos que recebam parâmetros e outros que não recebam.
2. Remova 4 caracteres do exemplo do método `devolveDois` de forma que continue compilando e funcionando do mesmo
jeito (em Scala em vários momentos existem notações mais curtas para declarações simples).
3. Implemente um método recursivo. A sintaxe de `if` é praticamente a do Java 

	if ( condicaoBooleana) codigo else codigoCasoFalse

