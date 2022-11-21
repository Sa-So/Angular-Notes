# Service is a normal ts class !! <3
- no @Decorater needed !
- this works but is not the right way :
![image](https://user-images.githubusercontent.com/60461699/202990866-e5bb94cb-e3bb-4e94-a87f-7a240643219a.png)
- What is the right way then ?
## here comes dep. inj.
- angular ecosystem. 
- providers:[LoggingService] - to tell how to create that service.
![image](https://user-images.githubusercontent.com/60461699/202991435-5847f040-49ab-4bc2-9ed5-818496915fb3.png)
# Data Service
- create
![image](https://user-images.githubusercontent.com/60461699/202992836-142e8e79-7fad-46da-a9ec-d4293141ec83.png)

- usage
![image](https://user-images.githubusercontent.com/60461699/202992470-2e70af4e-7052-4504-9a73-9b7477408bda.png)

- note: when we assign a variable inside an array from a service they ref to that array in that instance of that class/service.
- coz arrays are passed by reference in ts/js.

## ng dep. inj. is a Hierarchichal injector.
- the child comp. will receive this service auto ?!!
- so if we provide it to the appModule, the same instance of the service will be available to the whole fuckin app
- yes we can inject services into services lmao
- if we provide it to the appComponent, the same instance of the service will be available for **all components** (not **other services**)
- propagates down only , i.e. passes to child.
- we can override in child comp. tho by providing the class into providers array
- but if we leave it we will have access to same instance

## 111. injecting serv. into serv.
- we need to give metadata to our service via the decorator
- @Injectable to the service you want to inject the other service
- we can just always add this decorator

## cross - comp. commun
- add new event emitter in service
![image](https://user-images.githubusercontent.com/60461699/202995473-b9a369ce-3a57-4c8e-bc6a-c0284f1b220c.png)

- emit it in a component !
![image](https://user-images.githubusercontent.com/60461699/202995729-65c53678-8e13-4d79-b180-533f431b1786.png)


- listen to that event in any other component !
![image](https://user-images.githubusercontent.com/60461699/202995990-e603b881-f3e9-45db-b3ab-6ce63ebb522b.png)


- event emitter object kind of just wraps an observable ?
##
![image](https://user-images.githubusercontent.com/60461699/202996270-d06ed41d-9674-43ce-9410-e82746d67e78.png)



