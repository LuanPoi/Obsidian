Falando de maneira genérica, uma Intent é um objeto de mensagem que é usado para solicitar uma ação de outro componente do aplicativo ou até de outro aplicativo.

## casos de uso:
* iniciar uma activity
* iniciar um service
* enviar um broadcast

## tipos de Intent:
* Intent Explícitas
	* Intents que são explicitamente direcionadas para um componente específico.
		* Exemplo: abrir uma nova activity.
* Intent Implícitas
	* Intents que são definidas pela ação a ser executada.
		* Exemplo: abrir uma rota em um mapa ou a camera (onde o usuário pode escolher que aplicativo de mapa ou camera será aberto).

## Intent Filter
Configuração das Activities que indicam ao sistema quais são os eventos que o aplicativo é capaz de tratar.