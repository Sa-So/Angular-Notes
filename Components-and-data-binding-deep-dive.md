# basically taught how to pass props to child component.
# in react we could pass functions to change something in parent comp via child comp.
# in ng we Output('prop') prop = new eventEmitter() to do so.
# prop drilling


# local references.
- can only be used in templates not in ts code.

## we can replace two way binding with local ref in some scenarios.
- scenario: we only want the value of an input when we click submit or some button !
- so there is no need to update the variable in ts code with whatever there is in input every single time some key is pressed !
- so we can refer to that input element via putting #server-input attribute on it and then
- passing it to (click)="onClick(server-input)"
```ts
onClick(inp: HTMLInputElement){
  console.log(inp.value)
}
```


### we can fetch local references / components using @ViewChild(server-input) servInp : ElementRef;
- ElementRef is an angular type.
```ts
servInp.nativeElement.value
```
- don't access the dom / change it via this tho
- there is a better way of accessing dom in ng we will see in directives,

# use <ng-content> </ng-content> to render child components inside a component.



# lifecycle 
- useEffect alternatives haha
## ngOnInit()
- ng instantiates one of the component and adds it to the dom when it sees it in the html.
- this runs on initialization , but yet not added to the DOM
- object was created we can acess properties etc
- basically afte the constructor.
### which is a major difference b/n react and angular !!!!
- in react useffect only gets called after creating the dom once . even eith empty deps i think.

## ngOnChanges()
- multiple times
- exec right at start
- whenever @input changes.
 
 
## ngDoCheck()
- every change
- a button click
- a timer fired
- an observable was resolved ?! is he talking about promises ?
- manually inform ng


## ngAfterContentInit()
- ng-content change
## afterContentChecked
- every time projected content is checked ?
<!-- ![image](https://user-images.githubusercontent.com/60461699/202397338-86796466-770c-4545-b333-5331957c6d84.png) -->
![image](https://user-images.githubusercontent.com/60461699/202397449-3e0d59fd-324c-4c73-915c-85fcf65cbd13.png)

# I love Typescript
- we should write which interfaces this component is implementing sep via comma !!
## writing ngOnChanges() will do the trick but writing implements onChanges is a good practice.








