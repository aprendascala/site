---
layout: post
title: Covariância e Contravariância
permalink: /covariancia-contravariancia.html
category: tipos
---

Recentemente consegui entender como funciona [Covariância][1] e [Contravariância][1]. 

Em Scala, covariância pode ser denotada por `+T` (T é o tipo). Isso significa, que T pode ser **substituído**
por qualquer outro tipo que seja um filho dele. Por exemplo:

	class Covariancia[+T] {
	  val a : Covariancia[AnyRef] = new Covariancia[String]
	  val b : Covariancia[AnyRef] = new Covariancia[AnyRef]
	  val c : Covariancia[AnyRef] = new Covariancia[Any] // Não Compila
	}

Contravariância é o contrário. O tipo pode ser **substituído** por qualquer pai dele e é denotado por `-T`. Exemplo:


	class Contravariancia[-T] {
	  val a : Contravariancia[AnyRef] = new Contravariancia[String] // Não Compila
	  val b : Contravariancia[AnyRef] = new Contravariancia[AnyRef]
	  val c : Contravariancia[AnyRef] = new Contravariancia[Any]
	}

E, para complementar, invariância exige que você **substitua** apenas pelo mesmo tipo (denotado por `T`):

	class Invariancia[T] {
	  val a : Invariancia[AnyRef] = new Invariancia[String] // Não Compila
	  val b : Invariancia[AnyRef] = new Invariancia[AnyRef]
	  val c : Invariancia[AnyRef] = new Invariancia[Any] // Não Compila
	}

Uma coisa que é muito importante notar, é que isso é referente aos tipos genéricos e não à atribuição de variáveis,
retornos de métodos ou parâmetros passados à funções/métodos (isso confundiu a minha cabeça por muito tempo):

	class AtribuicaoInvariante[T](t : T) {
	  new AtribuicaoInvariante[AnyRef]("".asInstanceOf[Any]) // Não compila
	  new AtribuicaoInvariante[AnyRef]("".asInstanceOf[AnyRef])
	  new AtribuicaoInvariante[AnyRef]("")
	}

	class AtribuicaoCovariante[+T](t : T) {
	  new AtribuicaoCovariante[AnyRef]("".asInstanceOf[Any]) // Não compila
	  new AtribuicaoCovariante[AnyRef]("".asInstanceOf[AnyRef])
	  new AtribuicaoCovariante[AnyRef]("")
	}

	class AtribuicaoContravariante[+T](t : T) {
	  new AtribuicaoContravariante[AnyRef]("".asInstanceOf[Any]) // Não compila
	  new AtribuicaoContravariante[AnyRef]("".asInstanceOf[AnyRef])
	  new AtribuicaoContravariante[AnyRef]("")
	}

Nesses casos, ele sempre se comporta de forma análoga ao tipo Covariante.

Um outro lugar onde é possível notar covariância é no **tipo de retorno** de métodos, como em Java:

	trait RetornoCovariante {
	  def metodo : AnyRef
	}
	
	class TestString extends RetornoCovariante {
	  override def metodo : String = ""
	}
	
	class TestAnyRef extends RetornoCovariante {
	  override def metodo : AnyRef = ""
	}
	
	class TestAnyAny extends RetornoCovariante {
	  override def metodo : Any = "" // Não compila
	}

Já os **parâmetros declarados nos métodos** são invariantes:

	trait ParametroInvariante {
	  def metodo(v : AnyRef)
	}
	
	class TestString extends ParametroInvariante {
	  override def metodo(v : String) = "" // Não compila
	}
	
	class TestAnyRef extends ParametroInvariante {
	  override def metodo(v : AnyRef) = ""
	}
	
	class TestAnyAny extends ParametroInvariante {
	  override def metodo(v : Any) = "" // Não compila
	}

[1]: http://en.wikipedia.org/wiki/Covariance_and_contravariance_(computer_science)
