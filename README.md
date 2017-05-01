# Curso AngulaJS

   Esse repositório contém os códigos gerados a partir do estudo de AngularJS
   
## Conteúdo

  1. [Importar Biblioteca](#importar)
  2. [Declarar Módulo](#modulo)
  
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
   
   A segunda forma de declaração atribui a referência do módulo a  variável **app**.<br/>
   **Vantagem:** O módulo pode ser referenciado a partir da variável **app**;<br/>
   **Desvantagem:** O módulo fica exposto no escopo.
     
   
