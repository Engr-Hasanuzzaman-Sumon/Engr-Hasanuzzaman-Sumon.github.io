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
## for loop on collection example
```javascript
<li *ngFor="#item of items">
```
where `items` is the component class properties
`#item` create local reference that we can use like `{{ item }}` or `[value]="item"`

## Use on componetn with in another componet
If we want to use component `Comp1` with in `main` component we have to configure our component like

```javascript
@component({
	selector: 'main',
	directives: [Comp1]
})
```

## Angular 2 app root directory is app folder (from any where in the app)
so `foo.ts` means it is in application root directory
`templates/foo.html` means it is in templates directory under root directory


## templateUrl
We can keep template on separate folder. To use those template we will use `templateUrl` instead 
`template`

## Decorator
*Decorator* just `expression` that return something not `statement` that command compiler to do something.
So, `;` after *decorator* will introduce `ts` error 
