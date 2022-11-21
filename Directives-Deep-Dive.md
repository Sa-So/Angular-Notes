# atrrb & struct.
- we cannot have more than 1 structural dir. on any elem.
# basic attrb dir.
@Directive({
  selector:'[appHighLight]',
})

Now that would select it by element.

Now I want to have this attribute style,

so I'm going to wrap this in square brackets

which means this will now be recognized

whenever I add appBasicHighlight

without square brackets to an element.

## full file looks like
![image](https://user-images.githubusercontent.com/60461699/202983429-8c538694-a738-4009-b6a1-9058a13f8d34.png)
# better way.
> ng g d better-highlight
- using renderer2 https://angular.io/api/core/Renderer2
## why it's better ? (read transcript)
![image](https://user-images.githubusercontent.com/60461699/202984166-8a4120bd-72f1-4faa-8677-03ec966788a8.png)
# HostListener('mouseenter')
- to react to any events. built in or custom!
- event binding ?
- event data of type Event.
![image](https://user-images.githubusercontent.com/60461699/202984953-70b70a80-e383-4675-9892-cf52068c51f2.png)
# @HostBinding('styles.backgroundColor') varName:string;
- bind a variable to that property ! so when that var changes the prop on that element changes.
## weird stuff.
- we can use alias
![image](https://user-images.githubusercontent.com/60461699/202986199-d5e87cc5-9c0e-490f-a39c-3ab4a451af6c.png)
- and put a directive & get the input at the same time via [dir]="'red'"
![image](https://user-images.githubusercontent.com/60461699/202986260-cc712fc4-f2e2-4b94-9851-ac9f958a59f7.png)
- we can also omit square brackets and double quotation marks.= if the prop. binding is a string.
![image](https://user-images.githubusercontent.com/60461699/202986502-162645dc-782d-45a5-b789-bad0a29d35b5.png)
- but makesure it is property binding and not setting any attrb to that html by making the names pretty diff.

# BTS (struct. directives)
- this is what the star transforms into !
- you can totally get rid of stars lol 
![image](https://user-images.githubusercontent.com/60461699/202987506-a48e24d0-9ac7-4b7e-9a12-1b92e9410002.png)

# Building struct dir.
![image](https://user-images.githubusercontent.com/60461699/202988228-1ddcc692-3fc4-4035-924c-b630f090da9d.png)

![image](https://user-images.githubusercontent.com/60461699/202988282-4548ca4e-ac73-4928-9de2-f9198aae29a8.png)

- to use it like above , our property name should share the name of the directive selector!

# ngSwitch
![image](https://user-images.githubusercontent.com/60461699/202988747-ed1b14a0-54f3-4a62-81bf-a992bc2fc2a1.png)


# Course Project:
- dropdown directive !
![image](https://user-images.githubusercontent.com/60461699/202989822-233e1ea0-17b9-44ef-a418-fc4f542f21a2.png) 
![image](https://user-images.githubusercontent.com/60461699/202989736-951ac570-a64b-41c1-9004-e98eb599d52e.png)

- closing from anywhere:
![image](https://user-images.githubusercontent.com/60461699/202989608-96d7c585-6a6a-4abb-875c-84ec87269523.png)







