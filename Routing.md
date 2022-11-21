# create a var preferably appRoutes of type Routes ( which is an array )
1. add objects in it like {path:'users', component:UserComponent}
2. In @NgModule -> imports -> add RouterModule.forRoot(appRoutes)
3. add ```html <router-outlet> ``` where we want to change the comp. to render based on route

# change route by clicking buttons
1. adding href="/users" will reload the page which we don't want !
2. we can use routerLink = "/users"
3. or if non-string data we do [routerLink]="['/users','something']"

# paths
- leading / means absolute path.
- 'users' this is relative path & './users' is also a relative path ! 
- but '/users' this is an absolute path
- '../users' this remove one path before then add users

> Note : relative to the path of the current component in which the button to go to the route was not the route displayed on the top of browser.

# change css of link based on path
- using directive routerLinkActive which gets a class as inp.
- attach it to the wrapping element or the anchor link itself
- the link with route as / will always have that class added here is why :-
![image](https://user-images.githubusercontent.com/60461699/203029161-7cb5baef-542b-448f-8b85-217f6a78e65c.png)
- so /users has a / in it ?! wtf.
- to tackle this we add [routerLinkActiveOptions]="{exact:true}"
![image](https://user-images.githubusercontent.com/60461699/203028083-bd08f034-5971-459c-ad87-803c9d2c108c.png)


# navigating programatically (without any clicks.)
- inject the router.
- then use this.router.navigate(['server'])
- now navigate method is a bit diff , it doesn't know it's current component ! (router-link does)
- so if we want to make the navigation to a relative path we have to give one more thing as inputto the navigate function
- optional paramaeter relativeTo
- & we can get the current route by injecting ActivatedRoute ! 
![image](https://user-images.githubusercontent.com/60461699/203031520-d88e1da0-0352-4dde-9ca0-316833315aec.png)

## But I have a question !!!
- router-link is relative to the route of the comp it is in
- but this will be relative to whatever the current path is !! wouldn't it be ?!
- that means relative to whatever is being shown in the url of browser !


# passing parameters to routes
- use users/:id
# fetch parameters from curr route
- inject activated route
- this.route.snapshot.params['id']
# when curr route changes to itself but diff id , the component doesn't get re rendered/created so the variables hold the same old values !
- so we kinda do something like useEffect i.e. subscribe to params change of the injected route & update our comp. variables
![image](https://user-images.githubusercontent.com/60461699/203033973-afc77596-94f7-4d12-898c-be89e3b3cc8d.png)

- use implements onDestroy hook on that component to destroy the subscription yourself or ng will do it for you if you don't hehe
> we are using rxjs to get this functrionality of observables.
![image](https://user-images.githubusercontent.com/60461699/203034874-48bbf9ed-21ea-4cc5-871c-54772268eaaa.png)
- you have to unsubscribe if u create ur own observables !!

# query params
- [queryParams]="{allowEdit:'1'}" and other key value props.
- it is not a new directive it is a property that is bindable with the routerLink directive

- we can pass query params to navigate program. too just like the relative to inside the optional object param at last of .navigate

# fragment
![image](https://user-images.githubusercontent.com/60461699/203035914-e4a8b14e-9df1-47d5-a9d4-de4b81432718.png)
- we can only have 1 fragment .
- what's the use of fragments ?!
- just #loading

# retrieve them
- inject activatedRoute
- we can use snapshot
- also subscribe
- ng will hndle destruction


