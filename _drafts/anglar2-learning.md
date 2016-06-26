# Angular 2 learning note

## Component
A basic Component has two parts:

* A Component annotation
* A component definition class

```javascript
{{ name }}
```
is called template / mustache tags

The `*ngFor` syntax says we want to use the `NgFor` directive on this attribute.
`#name` is called a reference.

- We can assign value to component variable by passing value using `inputs`
ex: 
```javascript
@component({
	selector: 'foo',
	inputs: ['value'], // means we can pass value to component using `[value]='some-value'
	host: {
		class: 'kclass'
	}, // it will add class `klass` to every componet `foo`
	template: `
	// template defination

	`
});
```
-componet teach browser new tag
-An Angular 2 Application is nothing more than a tree of Components.
-application is top level component which has many child component
-when parent componetn rendered it recursively render all of it's children
-The @Component decorator is where you configure your component. Primarily, @Component will
configure how the outside world will interact with your component.
-There are two ways to use component selector. let `my-app`
	* use direcly selector tag with in html like `<my-app></my-app>`
	* use as attribute with regular `div` <div my-app></div>`
	


## for loop on collection example
```javascript
<li *ngFor="#item of items">
```
where `items` is the component class properties
`#item` create local reference that we can use like `{{ item }}` or `[value]="item"`

## Use on componetn with in another componet
If we want to use component `Comp1` with in `main` component we have to configure our component like
N.B: like angular 1 in angular 2 directives are not defalutly global. That's why we have to pass explicitely. 

```javascript
@component({
	selector: 'main',
	directives: [Comp1]
})
```
The [squareBrackets] pass inputs and the (parenthesis) handle outputs.
Data flows in to your component via input bindings and events flow out of your component through
output bindings.

### If we want different input name mapes to different propertis then
`inputs: ['name: shortName', 'age: oldAge']`
where componetn properties name are `name` and `age` but in view we expose `shortName`, `oldAge` respectively 
`<my-component [shortName]="myName" [oldAge]="myAge"></my-component>`

```javascript
class MyComponent {
name: string;
age: number;
}
```
More generally, inputs strings can have the format 'componentProperty: exposedProperty' .

## Angular 2 app root directory is app folder (from any where in the app)
so `foo.ts` means it is in application root directory
`templates/foo.html` means it is in templates directory under root directory


## templateUrl
We can keep template on separate folder. To use those template we will use `templateUrl` instead 
`template`

## Decorator
*Decorator* just `expression` that return something not `statement` that command compiler to do something.
So, `;` after *decorator* will introduce `ts` error 

## TypeScript
Type in typescript is optional.
Like es5, we can declare variable using `var` ex: `var name;` but in typescript we can tell optional type using `:` after variable name like `var name: string;`
similarly for function declaretion `function foo(): string{ }`

### Interactive typescript 
You can install 'tsun (TypeScript Upgraded Node)' for playing in typescipt
`tsun` as `node` package
install using `npm install -g tsun`
then use from terminal `tsun`

### `any`
any is the default type if we omit typing for a given variable. Having a variable of type any allows
it to receive any kind of value:

```javascript
var something: any = 'as string';
something = 1;
something = [1, 2, 3];
```
### constructor
In TypeScript you can have only one constructor per class. where  `es6` can have more then one constructor as long as `parameters` are different .

### Fat Arrow Functions `=>` 
When we need to pass function as parameter we have to write 
```javascript
array.forEach(function(n){
	
});
```
using `=>` we can simplified above function as 

```javascript
array.forEach((n) => {});
```

There is a diffence btw tow methods.
- With in first we do not get `this` reference with in parameter `function`
- With in second we do get `this` reference with in `=>` 
N.B: Need to read about `js scope`

### Template Strings
- String interpolation 
```javascript
`Hello ${firstName} ${lastName}`;
```
- Multiline string 
```javascript
var template = `
<div>
<h1>Hello</h1>
<p>This is a great website</p>
</div>
`
```