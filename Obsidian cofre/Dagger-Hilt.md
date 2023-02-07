# Resumo
Em resumo, o Dagger é uma biblioteca de injeção de dependência para Java, Kotlin e Android que ajuda os desenvolvedores a gerenciar e injetar as dependências automaticamente usando anotações.  

No Jetpack do Android o Google disponibilizou o Hilt, que é baseado no Dagger 2 e que vai ajudar a conectar as dependências com as classes Android.

O [[Dagger]] vai criar as instancias da classe e suas dependencias e o [[Hilt]] vai dizer o escopo de vida dessas instancias (elas devem morrer com o [[Fragment]], [[Activity]] ou [[Application]]), o [[Hilt]] define uma maneira padrão de fazer a injeção de dependência no aplicativo com o fornecimento de containers para cada classe android no projeto, e ela vai gerênciar isso tudo no automático com o ciclo de vida de cada classe.

# Configuração

## Definir dependências
```ts
// build.gradle
plugins {
	...
	id 'com.google.dagger.hilt.android'
}
android {
	...
	compileOptions {  
	    sourceCompatibility JavaVersion.VERSION_1_8  
	    targetCompatibility JavaVersion.VERSION_1_8  
	}
}
dependencies {
	def daggerHiltVersion = "2.44"
	
	implementation "com.google.dagger:hilt-android:$daggerHiltVersion"
	kapt "com.google.dagger:hilt-compiler:$daggerHiltVersion"
}

// Allow references to generated code
kapt {
	correctErrorTypes true
}
```

## Fornecer instância da aplicação

1. Criar uma classe `MyApplication` que extende da classe `Application` e declarar essa nova classe no [[Manifest]].
```xml
<application
	android:name=".MyApplication"
	...>
```

2. Anotar a classe `MyApplication` com a anotação `@HiltAndroidApp`

# Anotações  e elementos

## @HiltAndroidApp
Informar ao [[Hilt]] que a classe anotada é a classe que ele tem que usar como container das dependências do nível de aplicação (Dependências que ficarão vivas enquanto o App viver).

## @Module
Indica ao [[Hilt]] que a classe anotada é um módulo e que ela tem a função de informar ao [[Hilt]] como fornecer instâncias de determinados tipos.

### @InstallIn(*ESCOPO*)
Informa em qual classe do android o módulo vai ser usado/instalado.
Escopos:
* `SingletonComponent::class` (Escopo da aplicação)
	Enquanto a aplicação viver os elementos viverão

### EntryPoints
* `@AndroidEntryPoint`
	Feito na [[Activity]] e no [[Fragment]].
* `@HiltViewModel`
	Feito no [[ViewModel]].

### @Inject
Informa ao [[Hilt]] como ele pode fornecer a própria classe que tem essa anotação como dependência.

### @Binds
Informa ao Hilt qual implementação usar quando é necessário (Caso esteja sendo utilizado classes abstratas para a conexão).
A própria declaração passa várias informações ao [[Hilt]]:
- Tipo de retorno: Qual interface essa função fornece como instância.
- Parâmetro da função: Qual implementação fornecer

### @Provides
Mostra como uma instância é retornada (Normalmente quando a criação dessa instância não se dá por meio do construtor ou exige passos extras entre o recebimento de um parâmetro e a passagem do mesmo para o construtor da classe a ser retornada)