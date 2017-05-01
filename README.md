# Curso AngulaJS

   Esse repositório contém os códigos gerados a partir do estudo de AngularJS
   
## Conteúdo

  1. [Importar Biblioteca](#importar)
  2. [Declarar Módulo](#modulo)
  3. [Localizar Módulo](#localizarModulo)
  4. [Utilizqar Módulo](#utilizacaoModulo)
  5. [Declarar Controller](#declararController)
  
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
   Esse diretiva pode ser inserida em qualque elemento html. É recomendadoe que essa  diretiva seja inserida na tag *html*<br/>
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
   	
       angular.module("helloWorld").controller(nomeController,function ($scope){
       });
       
   O primeiro atributo é um objeto do tipo String que identifica o nome do controller; <br/>
   O segundo atributo é um **function** que contém as funcionalidades do controller; <br/>
   - A function recebe como parametro a variável *$scope* que representa o escopo; 
   

