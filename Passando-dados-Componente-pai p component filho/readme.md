
## No componente filho incluímos o decorator @Input(), definindo que a propriedade autor poderá ser alterada pelo componente pai. No exemplo ele vai passar a informação de nome para a variável autor.

## No componente pai incluímos o selector autoria , definido para componente filho, de forma a ser renderizado no selector artigo na tag <artigo> do arquivo index.html.

## A partir do componente pai, estamos definindo o valor da propriedade autor do componente filho. Para passar um valor para o componente filho, precisamos passar a propriedade do componente filho entre colchetes [] e definir seu valor para qualquer propriedade do componente pai.

## No exemplo, estamos passando o valor da propriedade nome do componente pai para a propriedade autor do componente filho.




### Componente Pai
	import { Component } from '@angular/core';
	@Component({
	  selector: 'artigo',
	  template:  `
	    <h1>{{titulo}}</h1>
	     <autoria [autor]="nome"><autoria>
	  `
	})
	export class AppComponent {
	  titulo:string = 'Banco de dados na Web';
	  nome:string = 'Macoratti';
	}




### Componente Filho
	import {Component, Input } from '@angular/core';
	@Component({
	  selector: 'autoria',
	  template: `
	    <h3> Escrito por : {{autor}} </h3>
	  `
	})
	export class AutoriaComponent { 
	    @Input() autor : string;
	}
 


Fonte: http://www.macoratti.net/17/07/ang2_pdtcomp1.htm