## String Interpolation
```html
{{Cid}}
```
- curly braces x 2
- anything that can be converted to a string at the end or returns a string like a function.
- cannot use multiline expressions , ifs elses but can use ternary.

## Property Binding
```html
<button [disabled]="!allow"></button>
```
- square brackets
- we can also call a method here :)

## we can replace string interpolation with property binding 
```html
<div [innerText]="allow"></div>
```
- don't mix them though

## Event Binding
```ts
(click)=""
```
- replace onclick with (click)="onClick($event)"
## Important: FormsModule is Required for Two-Way-Binding!

Important: For Two-Way-Binding (covered in the next lecture) to work, you need to enable the ngModel  directive. This is done by adding the FormsModule  to the imports[]  array in the AppModule.

You then also need to add the import from @angular/forms  in the app.module.ts file:

import { FormsModule } from '@angular/forms'; 

## 2 way data binding
- we combine property and event binding !
- easier !
- ngModel directive

## Directives
- are some instructions in the dom
- components are such kinds of instructions in the DOM (directives with a tempelate) (to place our component here etc.)
- we can build custom directives
- typically add directives via attribute selector
- selector of a directive can be configured like the selector of a component ! <app-selector> <>
  
### star 
- structural directives require a star ! like *ngIf
  - anything which changes the structure of our dom is structural 
## ngIf
- puts a hook in dom , to know where to enter element but doesn't hide and show element , instead create it at that place
### using else with ngIf
  - local reference ? a marker. #
 ```html
  <p *ngIf="serverCreated; else noServer">server was created</p>
  <ng-template #noServer><p>no server created !</p></ng-template>
 ````
## ngStyle - attribute directive
- attrb dir. only change the element they are placed on instead of the dom (i.e. they don't add or remove elements)
- pretty much usless without property binding
```html
  <p [ngStyle]="{backgroundColor: getColor()}"
```
- it accepts an object . the quotations tell us its ts.
- can use string 'background-color': or use the camelcase version allowed in js/ts like in react.
- calling a function proves tha we are writing ts code in html getcolor
## ngClass
- dynamically add or remove css classes like ngStyle dynamically changes styles.
- also accepts an object 
     where key : className and value: boolean value weather to attach it or not !
     
## *ngFor
![image](https://user-images.githubusercontent.com/60461699/202110888-f8de322b-bee0-4be6-a520-24218d429dd3.png)
# Project
- we can specify path in component name to make it inside a specific folder ! in the n g c --skip-test command.
- models , features , components
- we can use bootstrap for quick css !
![image](https://user-images.githubusercontent.com/60461699/202116769-ada7d6eb-20a4-44d6-a1ee-7d9c8f033240.png)

     
     
     
     
     
     
