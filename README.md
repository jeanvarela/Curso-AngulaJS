# Curso AngularJS

   Esse repositório contém os códigos gerados a partir do estudo de AngularJS
   
## Conteúdo

  - [Importar Biblioteca](#importar)
  - [Declarar Módulo](#modulo)
  - [Localizar Módulo](#localizarModulo)
  - [Utilizar Módulo](#utilizacaoModulo)
  - [Declarar Controller](#declararController)
  - [Utilizar Controller](#utilizarController)
  - [Manipular Scope](#manipularScope)
     - [Inserir variável no escopo](#inserirVariavelNoEscopo)
     - [Exibir informação do Escopo](#exibirInformcaoEscopo)
  - [Diretivas](#diretivas)
     - [ng-app](#ngapp)
     - [ng-controller](#ngcontroller)
     - [ng-bind](#ngbind)
     - [ng-repeat](#ngrepeat)
     - [ng-model](#ngmodel)
  
<a name="importar"></a>  
## Importar Biblioteca
  Antes de iniciar o projeto é necessário fazer download da biblioteca do AngularJS. Disponivel em [AngularJS](https://angularjs.org/).
  Importar a biblioteca no arquivo **html**:  

    <script src="lib/js/angular.min.js"></script>

  
<a name="modulo"></a>
## Declarar Módulo
   Um módulo é declarado através da seguinte expressão:
   
       angular.module(nomeModulo,[]);
       
   O primeiro parametro é um objeto do tipo String que identifica o nome do módulo;
   O segundo  parametro é um array  de String. Esse array é utilizado para a injeção de módulos.

   É possível declarar um módulo de duas forma:
   
       1) angular.module("helloWorld",[]);
            
       2) var  app = angular.module("helloWorld",[]);     
   
   A segunda forma de declaração atribui a referência do módulo a  variável **app**.
   
   **Vantagem:** O módulo pode ser referenciado a partir da variável **app**;<br/>
   **Desvantagem:** O módulo fica exposto no escopo.
     
<a name="localizarModulo"></a>
## Declarar o módulo
   Antes de usar o módulo é necessario localiza-lo. Para localizar o módulo é utilizado o seguinte comando:
           
        angular.module("helloWorld");
        
<a name="utilizacaoModulo"></a>
## Utilização Módulo
   A utilização de um módulo é através do uso da diretiva ng-app.<br/>
   Esse diretiva pode ser inserida em qualque elemento html. É recomendado que essa  diretiva seja inserida na tag *html*<br/>
   A seguir é apresentada a utilização na tag *body*
   
      <html ng-app="helloWorld">
         <head>
         </head>
         
         <body>
         </body>
      </html>
   
        
<a name="declararController"></a>
## Declarar o Controller
   O controller é declarado através da seguinte expressão: 
   	
       angular.module("helloWorld").controller("helloWorldCtrl",function ($scope){
       });
       
   O primeiro atributo é um objeto do tipo String que identifica o nome do controller; <br/>
   O segundo atributo é um **function** que contém as funcionalidades do controller; <br/>
   - A function recebe como parametro a variável *$scope* que representa o escopo; 
   
<a name="utilizarController"></a>
## Utilizar o controller
   A utilização de um controller é através do uso da diretiva ng-controller.<br/>
   Esse diretiva pode ser inserida em qualque elemento html ou até mesmo em uma div. <br/>
   A utilização *ng-controller* indica que a view e o controller  compartilham o escopo. A view é o local aonde essa diretiva foi colocada.
   A seguir é apresentada a utilização em um *div*:
   	
      <div ng-controller="helloWorldCtrl">
      </div>

<a name="manipularScope"></a>
## Manipular o Scope

<a name="inserirVariavelNoEscopo"></a>
### Inserir variável no escopo
   Para inserir uma mensagem no controller é utilizada a seguinte expressão:
  
   	$scope.message = "Hello World";
	   
   Essa declaração é inserida no corpo do controller:
   
   	angular.module("helloWorld",[]).controller("helloWorldCtrl",function ($scope){
	  $scope.message = "Hello World";
	});
	
<a name="exibirInformcaoEscopo"></a>
### Exibir Informação do Escopo
   Para exibir uma intormação do escopo é utilizado a interpolação da expressão entre **{{** e **}}**. <br/>
   A seguir é apresentada como é exibida a mensagem atribuida a variável *message* <br/>

      <div ng-controller="helloWorldCtrl">
	   {{message}}
      </div>
      
  Posteriormente será apresentada a diretiva **ng-bind** que também permite exibir mensagem do escopo.
   
<a name="diretivas"></a>
### Diretivas
   Um diretiva é uma extensão das tags do HTML. <br/>
   Com a criação de diretivas s]ao obtidos os seguinte beneficios:
* Definir novos comportamentos;
* Criar componentes reutilizáveis;

<a name="ngapp"></a>
#### ng-app
   Essa diretiva define as fronteira da aplicação. 
     <html ng-app="helloWorld">
     </html>
 
<a name="ngcontroller"></a>
#### ng-controller 
   Essa diretiva estabelece o vinvulo entre a view e o controller.
      <div ng-controller="helloWorldCtrl">
      </div>
    
<a name="ngbind"></a>
#### ng-bind 
   Essa diretiva faz a ligação da expressão na view com seu valor no escopo. Essa diretiva pega o valor no scope e envia para a view.
   No controller  é atribuida um valor a variável **message**:
   
      angular.module("helloWorld",[]).controller("controlador",function ($scope){
	   $scope.message = "Hello World";
      });

   Na view o valor de **message** é exibido em uma tag *H4*:
    
     <div ng-controller="controlador">
 	    <h4 ng-bind="message"/>
     </div>
     
   É prefirivel utilizar ng-bind ao invés de interpolação de expressão, pois com o uso da interpolação há possibilidade da expressão se exibida na tala caso a renderização demore.
   
   
<a name="ngrepeat"></a>
#### ng-repeat
  Permite iterar sobre coleções
  
      ng-repeat="elemento in listaElementos"
      
  A seguir é apresentado a utilização do ng-repeat em um tabela:
  ```
  angular.module("helloWorld",[]);
  angular.module("helloWorld",[]).controller("controlador",function ($scope){
	$scope.contatos = [
				{nome: "Funcionario 1", telefone: "81 - 9999999"},
				{nome: "Funcionario 2", telefone: "31 - 9999999"},
				{nome: "Funcionario 3", telefone: "21 - 9999999"}
			];
  });
  ```
  
  
 ```go
 <body ng-controller="controlador">
	<table>
		<tr>
			<th>Nome</th>
			<th>Telefone</th>
		</tr>
		<tr ng-repeat="contato in contatos">
			<th>{{contato.nome}}</th>
			<th>{{contato.telefone}}</th>
		</tr>
	</table>
</body>
 ```

<a name="ngmodel"></a>
#### ng-model
   Essa diretiva, assim como **ng-bind** realiza a ligação entre a view e o escopo, porém o **ng-model** insere o valor no escopo.
   
