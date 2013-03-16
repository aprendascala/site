---
layout: default
title: Classes
group: basico
---

A sintaxe para declaração de classes é parecida com a de Java:

	class NomeDaClasse {
		//métodos e atributos
	}

Mas muda quando declaramos um construtor:

	class ClasseScala(numero:Int) {
		// métodos e código do construtor
	}

Em Scala, todo o corpo da classe que não seja uma declaração de método ou variável é o código que é executado
quando o objeto é instânciado. A outra principal diferença é que a assinatura do construtor é definida logo após 
o nome da classe. Então, para instanciar a ClasseScala de executar:

	new ClassScala(100)

Scala possui um recurso chamado de `case class` que, além de definir a classe, ainda gera um monte de coisas úteis:

* Um método `toString` mais bonitinho
* `hashCode` e `equals` com base nos atributos declarados no construtor
* Métodos de acesso aos atributos declarados no construtor (o padrão em uma `class` é ser privado)
* Métodos para serialização
* Mais um monte de recursos

Um outro pequeno detalhe das `case class`, é que para instanciar você não precisa usar a palavra `new`:

	case class SuperCaseClass(algo:String)

	val a = SuperCaseClass("algo") // instância SuperCaseClass passando "algo" como parâmetro

## Exercícios:

1. Declare algumas classes (com e sem atributos) e instâncie elas.
2. Declare algumas case classes (com e sem atributos) e instâncie elas.
3. Imprima instâncias de classes e de case classes que tenham atributos com o mesmo nome. Veja as diferenças.

