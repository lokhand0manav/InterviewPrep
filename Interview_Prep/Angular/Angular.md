- ## Reference : https://www.youtube.com/watch?v=-jeoyDJDsSM
	- AngularJs vs Angular
		- AngularJs was version : 1.X
		- Mainly on javascript
		- No server side
		- Controlller architecture
		- Angular is anything above that
		- TypeScript based
		- Servder side
		- Component architecture
	- **Directives** in angular: DIrectives are Angular code in HTML tags:
		- `[()], {{}}, []`
		- ![[Pasted image 20220903163836.png]]
		- Structural (S)
			- Change the Structure of the DOM element. 
			- `*ngFor`
			- Mostly Structural Directives have a `*` in them
		- Attribute (A)
			- Just like normal attribute : `[hidden]` etc
		- Component (C)
			- A component created with a @Component decorative and a selector. Using this selector you call this particular component within HTML.
			- Most of the angular component are called using this component directive
			- `<ng-root\>`
	- **Type script** is something that adds Types to javascript
		- Makes javascript strongly typed
		- DOes have OOP 
		- Being strongly typed it has most of the errors handled during compile time.
	- **Decorator**:
		- ![[Pasted image 20220821120226.png]]
		- [[Angular_Decorator]]
		
	- **Types of Data Binding in Angular** 
		- `[]` <- Property Binding *(Controller to View)* 
		- `{{}}` <- Expression binding (Interpolation binding) You might have seen this in React as well 
		- `()` <- Event binding *(View to Controller)*
		- `[()]` <- Two way binding *(Controller to view by `[]`  & View to Controller by `()`)*
		- ![[Pasted image 20220821121325.png]]
		- Difference between property binding and interpolation:
			- We can use interpolation to set the value of properties as well, but in case of certain properties, interpolation wont work.
			- eg: `disabled` -> here if you set false or true to disabled with interpolation, html will consider this to be disabled only. but if you use property binding over `[disabled] = "isDisabled"` <-- this will work
	- **Architecture of Angular**
		- 1. Component -> binds css, templates logic..
		- 2. Template -> Has the view
		- Binding is done to bind the template i.e. view to component.
		- Modules collate the component together
		- view (template) has directives in it
		- service are some common code which will be used by multiple components or even modules
		- Dependency injection is used to inject the object of Service
		- ![[Pasted image 20220821123032.png]]
		- ![[Pasted image 20220821123155.png]]
	- **SPA**
		- load UI once, and dont reload again and again
		- Needed UI components/ artifacts are loaded on demand
	- **Angular Routing** : Helpful in implemeting SPA in Angular
		- Routing is simple URL, and the components which will get called when this URL is being called.
		- ![[Pasted image 20220821123617.png]]
		- To implement routing we need 3 things:
			- Collection : having the list of json which define the URL, and components to be loaded for those URL, and authGuard if required.
			- `<router-outlet>` in the HTML, where exactly the router will render the component
			- `[routerLink]` property directive <-- from HTML
			- incase of from component `.route.navigate(['*url*'])`
	- **Lazy Loading**
		- On demand loading, loading when its necessary
		- use load-children in your Router collection and load that particular module here.
		- Dividing your application into module is also necessary 
	- **Dependency Injection**
		- It is a Design pattern in which rather than creating the object of a class say O within the class say A, the object O is injected in the class A via its(As) constructor.
		- This job is handled by Angular
		- There is a `providers` property which belongs to `@NgModule` decorator
		- ![[Pasted image 20220821125316.png]]
		- ![[Pasted image 20220821125333.png]]
	- **ng server vs ng build**
		- ng server : builds in memory , great for development
		- ng build : builds on the storage, great when on production
			- creates a dist folder <-- the  compiled code is here
		- -- prod in build : does minification, comments, makes the code compress (just like grunt)
- Angular app is an interaction of following Angular artifacts:
	- Components
	- Services
	- Directives
	- [[Angular_Pipes]]
	- Modules
- ## Ref : https://www.youtube.com/watch?v=3dHNOWTI7H8&t=217s
	- MEAN stack : Mongo, Express, Angular Nodejs.
	   - Angular can be used on server side using `Angular Universal`
	- While creating a new app : ng new my-app
	   - CLI asks for stricter type check or not
	   - Router to be added or not
	   - Stylesheet type whether css or not
	- Default angular port : `4200`
	- main.ts is the entry point of Angular
	- EventEmitter can be used when you want to emit an event to another components.
	   - Eg : you create a `button` component which can be reused. You add a click event, but you will have to give the `click` event within the same component only, what you could do is: you will add an `EventEmitter`, and output that to the component which will call your button component, and use that emmiter there.
	- ? This is called optional
	- There are Observable in Angular present in RxJs
	   - Subscription, Observable :
	-   `href` of `<a>` will refresh the page. We dont want that we can use : `routerLink`
- ### Ref : https://github.com/sudheerj/angular-interview-questions
	-  Angular Architecture :
		- ![[Pasted image 20220902231754.png]]
	- Angular has the below key components,
		1.  **Component:** These are the basic building blocks of angular application to control HTML views.
		2.  **Modules:** An angular module is set of angular basic building blocks like component, directives, services etc. An application is divided into logical pieces and each piece of code is called as "module" which perform a single task.
		3.  **Templates:** This represent the views of an Angular application.
		4.  **Services:** It is used to create components which can be shared across the entire application.
		5.  **Metadata:** This can be used to add more data to an Angular class.
	- Directives add behaviour to an existing DOM element or an existing component instance. A component(@component) is a directive-with-a-template.
		- ![[Pasted image 20220902234030.png]]
	- Lifecycle hooks in Angular :
		- ![[Pasted image 20220902234630.png]]
			1.  **ngOnChanges:** When the value of a data bound property changes, then this method is called.
			2.  **ngOnInit:** This is called whenever the initialization of the directive/component after Angular first displays the data-bound properties happens.
			3.  **ngDoCheck:** This is for the detection and to act on changes that Angular can't or won't detect on its own.
			4.  **ngAfterContentInit:** This is called in response after Angular projects external content into the component's view.
			5.  **ngAfterContentChecked:** This is called in response after Angular checks the content projected into the component.
			6.  **ngAfterViewInit:** This is called in response after Angular initializes the component's views and child views.
			7.  **ngAfterViewChecked:** This is called in response after Angular checks the component's views and child views.
			8.  **ngOnDestroy:** This is the cleanup phase just before Angular destroys the directive/component.
- ### Ref : https://www.youtube.com/watch?v=-9VcW7MBDs8
- ProvidedIn under @Injectable for service has providedIn key
	- if given root the object of the service is injectable throughtout the app
	- if a module is given then it is only available in that module
	- ![[Pasted image 20220903171556.png]]
- `export default` vs `export`: https://stackoverflow.com/questions/33611812/export-const-vs-export-default-in-es6
	- when you just `export` while importing it is expecting exact name : `{}` but in case of `export default` you don't need curly braces
- ### Ref: https://www.youtube.com/watch?v=IYI0em-xT28
	- using # you can create a template variable. In this video it was used for formValidation
		- These template variables can be used from one part of template in another part of it