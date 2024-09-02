Angular 16
What you should already know?
1.	Html, Document object mode (DOM), Css, but isn't a must-have
2.	JavaScript
3.	Typescript
4.	It  also requires the basic concept of OOPs.
5.	NO Angular 1 or Angular2 or angular4 or Angular5 or Angular6 or Angular7,8,9,10,11 knowledge is required
# Why Developers choose Angular
  *Separation of DOOM manipulation logic from Application Logic
	We all now DOM stands for Document Object Model, it is a tree-structured model created in the page. In we 	applications, developed by using plain JavaScript or jQuery, developers need to write code manually to update the 	HTML element such as add/ remove, etc.
	In Angular, the DOM manipulation logic is completely eliminated which means developers don't need to write code for manipulation of HTML elements at run time, the angular framework itself does it.
* Separation of HTML Login from Application Logic
	HTML logic is the actual html code to design user interfaces. In web application developed by using javascript or jQuery, the developers write some pieces of HTML codes as part of javascript/jQuery.
	For eg: we use a jQuery append function to add HTML code dynamically. In that way, our code will mix up with application logic and design logic. This is not a good pattern, it is difficult to identify what element will represent on the screen at different states of the page.
	To overcome this problem, an angular framework is designed in such a way that application logic is separated from 	html logic. Thus in angular html logic is written in the template and application logic is written in components. Application logic will supply data to design logic and also contains event handlers to response to the user 	events.
	Business logic is the code where we fetch the data from data sources by making ajax calls and code for custom 	validations; this business logic must be independent of design logic because business logic must be usable event 	if design logic is not completed. 
	In Angular, services are classes containing business logic code. Service interacts with a servers by making ajax 	request to the API server and provides the validated data back to the component.
* Easy code maintanance
	In angular, we use module concepts in order to group the different components of different module and submodules of the project.
	For e.g.: In ERP Solutions, we have different modules such as finance, IT, etc. We can also share the components 	among multiple components.

* Develop single page application more easily
	Single page application is an application where navigation links never refresh the entire page. Angular provides an excellent concept called routing.
	For eg: User is viewing the dashboard page currently. So, the URL is www.example.com/dashboard. It the user 	copy/pastes the same URL into another tab, he will get exactly the same dashboard. Along with this, we can also 	implement user-level security to routes as well.
* Make the coding unit testable
	Unit testing is a concept of testing individual components or services without the integration of the completed application.
* Popular Companies Using Angular
•	Youtube
•	Google Cloud
•	Nike
•	HBO
•	Sony
•	Crunchbase
•	Conclusion
# Main Building Block of an Angular Application
Following are building blocks of Angular. These are:
	Modules
	Components
	Templates
	Metadata
	Data Binding
	Directives
	Services
	Dependency Injection

#Module:
Every Angular application must have at least one module. If angular application contains only one module, it is referring as root module. Every Angular application has one root module and many more featured modules.
angular module is a class which decorated with @NgModule. NgModule takes single metadata object and it’s properties describe the module. Following are the important properties of NgModule. 
•	Exports - It is the subset of declaration which would be used in the component template of other module.
•	imports - import other modules
•	providers - It is creator of services. They can be accessible in all the parts of the application. 
•	bootstrap - The root module has to set the bootstrap property. It is used to hos all other views. 
•	declarations - It declare the view class that belong to current module. There are three type of view classes supported by Angular components, directives, and pipes.
# Components:
The Component is class with the template that deals with the View of application and it's containing the core logic of the page. We can compare it with the Controller in Angular 1.x. We need to write the application logic inside the class which is used by the View. The component class interacts with the View through Methods and Properties of API.
import { Component } from '@angular/core'
@Component ({
 selector: 'test-app',
 template: '<h1>This is my First Angular 2 Application</h1>'+
 '<br/>'+
 '<input #txtName type = "text" (keyup)="0">'+
 '<br/>'+
 '<p>You have Enter: {{txtName.alue}}</p>'
})
export class AppComponent{
}

# Template: 
The template is the component View that tells Angular how to display the component. It looks like normal HTML.

template: '<h1>This is my First Angular 2 Application</h1>'+
 '<br/>'+
 '<input #txtName type="text" (keyup)="0"/>'+
 '<br/>'+
 '<p>You have Enter: {{txtName.value}}</p>'
})

# Service:
Service in Angular is a function or an object that can be used to share the data and the behavior across the application. It is JavaScript function which is used to perform a specific task. It includes the function, values, or any other feature required by the application. Typical examples of services are logging service, data service, message service etc. There is no base class for service.

# Directive:
Basically, directives are used to extend the power of the HTML attributes and to change the appearance of behavior of a DOM element.
Directive in Angular is a JavaScript class, which is declared as @directive, Angular has 3 types of directives, which are listed below--
1.	Component Directives
2.	Structural Directives
3.	Attributes Directives

# Dependency Injection
Dependency Injection is a software design pattern in which objects are passed as dependencies. It helps us remove the hard coded dependencies, and make s dependencies configurable. Using Dependency Injection, we can make components maintainable, reusable, and testable.
Point to remember about Dependency Injection, 
	it is stimulated into the Angular framework so that it can be use anywhere in an application.
	The injector is a main mechanism to maintain the service instance and can be created using a provider.
	The provider is the way of creating a service.
	We can register the provider along with injector.

# Basic Architecture of an Angular Application
# Angular Environment Setup
To set up Development Environment for Angular 2+, we required the following-
	IDE for writing your code (Editor)
	Nodejs
	NPM
	Angular CLI
# IDE for writing code (Editor)
There are many editor that can be used for Angular 14 development such as Visual Studio code and WebStrom. In this course we will use the Visual Studio code, which is free from Microsoft. 
Installation of Visual Studio Code
•	Some feature of Visual Studio Code are following-
•	Light editor as compared to the actual version of Visual Studio.
•	It can be used for coding language such as Clojure, Java, Objective-C, and many other languages.
•	It supports build-in Git extension so that you can or with source control without leaving the editor.
•	It includes built-in support for IntelliSenes code completion, rich semantic code understanding and navigation, and code refactoring.
•	It includes an interactive debugger, so you can step through source code, inspection stacks, etc..
•	Many more extensions for development.

# Angular CLI:
To install Angular cli globally on you system type "npm install -g @angular/cli". It install Angular CLI globally where g s referred to globally.
Example: 
npm install -g @angular/cli

If you want to make sure you have correctly installed the angular CLI, open the Visual Studio integrated terminal and type ng -v. If you can see the cli version as shown below, then installation is completed.

#Some common command 
•	Verify if npm is installed or not : npm -v
•	Verify the installed version of the node: npm -v
•	Verify if node is installed or not: node -v
•	Verify the installed version of the node: node -v
•	To install angular cli globally on your system type: npm install -g @angular/cli
•	to check correctly installed the angular CLI : ng v

Why does Angular 16 need Node.js?
Node.js is server-side platform build on Google Chrome's JavaScript Engine (V8 Engine). Node.js was developed by Ryan Dahl in 2009.
Node.js is an open source, cross-platform runtime environment for developing server-side and networking applications. Node.js applications are written in JavaScript, and can be run within the Node.js runtime on OS X, Microsoft, Windows, and Linux.

Node.js also provides a rich library of various JavaScript modules which simplifies the development of web application using Node.js to a great extent.
•	Node.js is an open source server environment
•	Node.js is free
•	Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc).
•	Node.js uses JavaScript on the server.

Node.js = Runtime Environment + JavaScript Library
Where to use Node.js?
Following are the areas where Node.js is proving itself as a perfect technology partner. 
•	I/O bound Applications
•	Data Streaming Application
•	Data Intensive Real-time application (DIRT)
•	JSON APIs base Applications
•	Single Page Applications
Why does Angular 16 need Node.js ?
	 Node allows you to spin up a lightweight web server to host your application locally in your system.
	 NPM (Node Package Manager) comes with node.js by default. NPM allows you to manage our dependencies. So, you don't have to worry for operations like adding a dependency, removing some, updating your package.json
	 Third and the most important, npm gives you angular cli or ng cli(angular command line interface). Angular CLI is a great too for scaffolding you application. So, you don't need to write boilerplates manually.
	 Angular recommends the use of TypeScript. Now, your browser does not understand Typescript. It need to be transpiled to JavaScript. Also, you need to bundle your js files and stylesheets together with the html doc so as to get the web app CLI which is ready to be hosted. Angular CLI helps you to do all these behind the scene. By default, ng cli uses webpack for bundling you application and is very helpful for beginner show have just jumped into web development with angular as it abstracts such complexities.

# What is Angular CLI?
The Angular CLI is a command-line interface tool that you use to initialize, develop, scaffold, and maintain angular application directly from a command shell.
Install node.js first if not already install (which I think you probably would have downloaded)
Open the node.js command prompt and issue the command:
Install the CLI using the npm package manager:
>> npm install -g @angular/cli

Note: The -g flag in the above command signifies the fact that the ng-cli is being installed in a global scope.
If you want to check out the latest vrsion of angular cli, modify the above stated command as: 
install the lates CLI using the npm package manager:
>> npm install @angular/cli@latest
# Package.json file and package-lock.json file?

package.json: 
This file is mandatory for every npm project. It contains basic information regarding the project (name description, license  etc), commands which can be used, dependencies - these are packages required by the application to work correctly, and devDependencies - again the list of packages which are required for application however only during the development phase. i.e. wee need Angular CLI only during development to build a final package however for production we don't use it anymore.

It allows future devs and automated systems to download the some dependencies as the project. It also allows you to go back to past versions of the dependency tree without actually committing the node_modules folder.

packages-lock.json records the same version of each installed package which allows Future install will be capable of building an identical dependency tree.
# Booting process of an Angular application OR What is workflow of an Angular Application?
	Angular application workflow
	Index.html↴
•	main.ts ↴
o	appmodule.ts ↴
	appcomponent.ts ↴
•	Appcomponent.html
# Angular Module:
Module in Angular refers to a place where you can group the components, directives, pipes, and services, which are related to the application.
In case you are developing a website, the header, footer, left, center and right section become part of a module.
# Angular Decorators:
•	* Decorators are a feature of TypeScript and are implemented as functions. The name of the decorator starts with @     Symbol following by brackets and arguments, since decorators are just functions in TypeScript.
•	Decorators are invoke at runtime.
•	Decorators allow you to execute functions. For example @Component executes the Component function imported from Angular 16.

# Common Decorators
•	@NgModule() to define modules...
•	@Component() to define components...
•	Injectable() to define services...
•	Input() and @Output to define properties... that send and receive data from the dom.
There are many build-in decorators available in Angular... and many properties on each decorator
Each decorator has a unique role.
# @HostListener()
* This is a function decorator that accepts an event name as an argument. When that event gets fired on the host element it calls the associated function.
# Components
Components are the most basic user interface building block of an Angular application. An Angular application contains a tree of angular components.
A components is nothing more than a simple TypeScript class in which you can create your own methods and properties according to your needs. which is use to bind with a UI (HTML page or cshtml page) of our application. The most import and feature of any Angular application is the component that controllers View or the template that we use. In general, we write all the application logic for the view that is assigned to this component.
Therefore, an Angular application is just a tree of such Components, when each Component is processed, it recursively processes its children Components. At the root of this tree is the top level component, then main component. 
When we bootstrap an Angular application, we tell the browser to render that top level root Component which ren does its child component and so on.

# Selector in Angular
The selector attribute allows us to define how Angular is identified when the component is used in HTML. It tells Angular to create and insert an instance of this component where if finds the selector tag in Parent HTML file in your angular app.
The selector accepts a string value, which is the CSS selector that Angular will use to identify the element. We will use it in html to place this component where we want. If you see the index.html file, you will find <app-root></app-root> component inside the body.
The component selector is a CSS selector that identifies how Angular finds this particular component in any HTML page. In general, we use element selector <app-root></app-root>, but it can be any CSS selector, form a CSS class to an attribute as well.
The component is applied to the <app-root></app-root> tag in index.html. If index.html does not have the tag, Angular will fail at startup. You can check where the Angular application will played. 
For example, here are some ways you can specify the selector attribute and how to use it in HTML 
•	element-name: Selector by element name.
•	.class: Selector by class name.
•	[attribute]: Select by attribute name.

# Template & templateURL
We know that the @Component decorator function take an object and this object contains many properties. So we will learn about the properties of the template & templateURL in this article.
We can render our HTML conde within the @Component decorator in two ways.
Inline Templates
The Inline templates are specified directly  the component decorator. In this, we will find the HTML inside the Typescript file. This can be implemented using the "template" property.
The literal values of the template with back-ticks marks allow string on multiple lines. It means that if you have HTML on more than one line, you should use backticks in side of single or double quotes, as shown below.
External Template
The External templates define HTML in a separated file and refer to this file in templateURL. means in this, we will find a separate HTML file instead o finding the HTML inside the TS file. Here, the TypeScript file contains the path to that HTML file with the help of the "templatreUrl" property.

# Style & StyleURL
We know that the decorator functions of @Component take object and this object contains many properties. We can represent our styles, i.e. the CSS code within the @Component decorator in two ways. 
Inline Styles
The Inline Style are specified directly in the component decorator. In this, you will find the CSS witing the TypeScript file. This can be implemented using the "style" property.
External Styles
The External style define CSS in a separate file and refer to this file in styleUrl. means In this, will find a separate CSS file instead of finding a CSS within the TypeScript file. Here, the TypeScript file contains the path to that style sheet file with the help of the "stylesUrls" property..

# preservewhitespaces
We know that the decorator functions of @Component take object and this object contains many properties. Using this property, we can remove all whitespaces from the template. It takes a Boolean value, that is : 
If it is false, it will remove all whitespace from the compiled template.
If it is true, it will not remove whitespace form the compile template.
preserveWhitespaces with true
Use the following code in app.component.ts file.

# viewProvider
We know that the decorator functions of @Component take object and this object contains many properties.
The viewProvider property allows us to make providers available only for the component's view.
When we want to use a class in our component that  is defined outside the @Component() decorator function, then first of all, we need to inject this class into our component, and we can achieve this with the help of the "viewProvider" property of a component.

# Encapsulation: In OOPs -> Wrapping the data and methods in a single unite is called encapsulation.
 BUT
In Angular 
To emulate the shadow DOM and encapsulate styles, Angular provides three types of view encapsulation. Are the following:
Emulated (default): The main HTML styles are propagated to the component. They styles defined in the component's @Component decorated are limited to this component only.
Native/shadow dom: The main HTML styles are not propagated to the component. the styles defined in the component's @Component decorator are limited to this component only.

None: The component styles are propagated to the main HTML and therefore are visible to all component of the page. with apps that have None and Native components in application. All components with encapsulation None will have either duplicate styles on all components with native encapsulation.
	Emulated : 
o	No Shadow DOM
o	Style encapsulation
	Native   : 
o	Shadow DOM
o	Style encapsulation
	None 	 : 
o	No shadow DOM
o	No Style encapsulation

# Provider Property
providers metadata is available in the @NgModule() decorator and @Component() decorator. provider's metadata is used to configure the provider.
A provider provides concrete and runtime version of a dependency value. The injector injects the objects provided by provider into components and services. Therefore, it is necessary to configure a service with the provider, otherwise the injector will not be able to inject it.
The injector injects the objects provided by provider into component and services. Only those classes configured by providers are available for dependency injection (DI).
Providers Property
•	Module Level
•	Component Level

# Parent to child communication with property
input property : 
Input property is used within one component (child component) to receive a value from another component (parent component). This is a one-way communication from parent to child. A component can receive a value form another component through component input property.
# Child to Parent communication with property
output Property
Input property is used send data from on component (child component) to calling component(parent component). This is a one-way communication from child to parent. this property name become a custom event name for the calling component. The output property can also create an alias with the property name as Output (alias) and now this alias name will be used in the custom event link in the call component. Now we will see how to use the output property.
It is the topic of the Component Interaction in angular. As we know, the angular application is based on small components, so it is very difficult to pass data from a child component to a parent component, in this scenario the output property is very useful. The angular component have a better way of notifying the parent components that something has changed through events. The "output" identify event that a component can fire to send information from the hierarchy to its parent from its child component.
# Directives in Angular-16
Directives: 
Basically, directives are used to extend the power of the HTML attributes and to change the appearance or behaviour of a DOM element.
Directive in Angular is a JavaScript class, which is declared as @directive. Angular has 3 types of directives, which are listed below-
1.	Component Directives
2.	Structural Directives
3.	Attributes Directives
Component Directives: 
	This is he special directive which is always present in angular app where each of our HTML page associated with this directive. (The directive with a template.)
	Component Directive is a class with @Component decorator function. As we know that angular app contains at least one component called AppComponent which is present inside the App-Component .ts file.
	In this file, we see with the help of selector, @Component which is a decorator function is used to create a component directive.
	Event if we create our on component, we will use this decorator function and creating a component directive. It is not possible to render our template without using "selector" property, so with the help of this property, we will create a component directive.

Structural Directive: 
	Structural directives are a key part of Angular everyone should be familiar with. They are responsible for manipulating DOM through adding , removing or changing the elements. Even if you have never written a structural 	directive yourself, you have probably been using *ngIf and *ngFor in your templates pretty often. The asterisk(*) states it is a structural directive.
	In other words, Structural directives are directives which change the structural of the DOM by adding or removing its elements. Structural directives reconstruct the layout by adding, removing, and replacing elements in DOM. The structural directives are responsible for shape or reshape the DOM's structure, typically by adding, deleting, or modifying elements. Similar to the other directives, you apply the structural directive to a host element. The directive then perform whatever it is intended to do with that host element. The structural directive are very simple to recognize. An asterisk(*) proceeded the directive attribute name. It does not require brackets or parentheses like attribute directive. These directives are the way to handle how the component or the element renders in a template.
There are basically 3 built in structural directive available in Angular.
1.	NgIf (*ngIf)
2.	NgFor (*ngFor)
3.	NgSwitch (*ngSwitch)
# *ngIf, else and then:
Here we will understand using NgIf with HTML elements. NgIf is an angular directive that is used to add an element subtree for true value of expression. NgIf is used as *ngIf="expression". Here if "expression" value is either false or null, in both cases the element subtree will not be added to DOM.

* NgIf conditionally includes a templates based on the value of expression.
* It adds or removes the HTML element DOM layout.
* The basic syntax of the ngIf directive is simple ;and effective, all we need to do is prefix the directive name with an asterisk(*) and add it anywhere inside our template.

NgIf is an structural directive that can add or remove host element and its descendants in DOM layout at run time. It conditionally shows the inline template.

ngif works on the basis of true and false result of given expression. If condition is true, the elements will be added into DOM layout otherwise they will removed. 
	<div *ngIf="condition"></div>

*ngIf with else

We will use NgIf with else. In our application else is used when we want to display something for false condition.
The else block is used as follows.
	<div *ngIf="condition; else elseBlock">...</div.
	<ng-template #elseBlock>...</ng-template>

For else block we need to use <ng-template> element. It is referred by a template reference variable. NgIf will use that template reference variable to display else block when condition is false. The <ng-template> element can be written anywhere in the HTML template but it will be readable if we write in just after host element of NgIf. In the false condition, the host element will be replaced by the body of <ng-template> element.

*ngIf with else and then

We will use NgIf with then and else. then template is the inline template of NgIg and when it is bound to different value then it display <ng-template> body having template reference value as the value. NgIg with then and else is used as follows.
	<div *ngIf="condition; then thenBlock else elseBlock"</div>
	<ng-template #thenBlock>...</ng-template>
	<ng-template #elseBlock>...</ng-template>

When condition is true, then the <ng-template> with reference variable thenBlock is executed and when condition is false then the <ng-template> with reference variable elseBlock is executed. The value of thenBlock and elseBlock can be changed at run time. We can have more than one <ng-template> for then and else block and at runtime we can switch to those <ng-template> by changing the value of thenBlock and elseBlock. At one time only one <ng-template> for thenBlock or elseBlock will run.

# ngSwitch in Angular-16

NgSwitch is an angular directive that displays one element from a possible set of element based on some condition.

NgSwitch uses ngSwitchCase and ngSwitchDefault. NgSwitch uses ngSwitchCase kyword to define a set of possible element trees and ngSwitchDefault is used to define default value when expression condtion does not match to any element tree defined by ngSwitchCase. NgSwitch is used as  property binding such as [ngSwitch] with bracket[]. To define possible set of elements, we need to add asterisk(*) as prefix to the switch case keywords as *ngSwitchCase and *ngSwitchDefault.

NgSwitch is a directive which is bound to an expression. NgSwitch is used to display on element tree from a set of many element trees based on some condition. It uses three keywords as follows.

ngSwitch: We bind an expression to it that returns the switch value. It uses property binding.
ngSwitchCase: Define the element for match value. We need to prefix it with asterisk(*)
NgSwitchDefaul: Defines the default emelent when there is no match. We need to prefix it with asterisk(*).

# ngFor in Angular-16

Angular provides NgForOf directive. If instantiate a template of revery element of given iterator. NgForOf has different local variable that can be used in iteration. The local varialbe are index, first, last, even, odd and ngForOf. NgForOf is used wit HTML elements as well as <ng-template>. Whenever the contents of iterates changes, NgForOf performs respective canges in DOM.

NgForOf provides several exported value that can be aliased to local variables. 
o	index: Index of current item.
o	even: True for an event index.
o	odd: True for an odd index.
o	first: True for first item.
o	last: True for last item.
	Index - Used for provide the index for current element while iteration.
	First - Return true if current element is first element in the iteration otherwise false.
	Last - Return true if current element is last element in the iteration otherwise false.
	Even - Return true if current element is even element based on index in the iteration otherwise false.
	Odd - Return true if current element is odd element based on index in the iteration otherwise false.
	NgFor is a structural directive change in DOM.
	It's point is to repeat a given HTML template once for each value in an array, each time passing it the array value as    context of string interpolation or binding.
	The syntax is *ngFor="let <value> of <collection>"
	<value> is a variable name of your choosing, <collection> is a property on your component which holds a collection, usually an array but anything that can be iterated over in a for loop.
Sometimes we also want to get the index of the item in the array we are iterating over.
We can do this by adding another variable to our ngFor expression and making git equal to index, The index is always zero based, so starts at 0 then 1, 2, 3, 4, etc...

# TrackBy with *ngFor:
The use of trackBy it's performance optimization and is usually not needed by default, it's in principle only needed it running into performance issues.
Suppose we have some data coming from some API request into the collection and we need to change the data over the web page using ngFor directive. In this case, Angular 7 will remove all the DOM elements that associated with the data and will create them again in the DOM tree, even the same data is coming (as shown in below screenshot). That means a lot of Do manipulation will happen if a large amount of data coming from the API.
The solution is, we can use trackBy function, which will be helpful for Angular to track the items which have been added or removed. 
TrackBy function will take two arguments first is index and second is current item and we can return the unique identifier as a return argument.
trackByStudetId(inde:number, student;any):string{
	return student.studentId;
}
# Grouping with *ngFor -> nested *ngFor   loop inside loop
# ngStyle
The NgStyle directive allow you to set a given DOM elements style properties.
One way to set style is by using the NgStyle directive and assigning it an object, like so:

<div [ngStyle]="{'background-color': 'green'}">Hello world</div>
This sets the background color of the div to green.
# ngClass
ngClass directie allows us to set the CSS class dynamically for a DOM element.
	ngClass with string
	ngClass with array
	ngClass with object
	ngClass with component method
# Data Binding in Angular-16
Data Binding means to bind the View (Html content) with Controller's (Component's) field. That is whenever we display dynamic data on a view (HTML) from component, data binding is used.

Data Binding basically means interacting with data. So, We can say that the interaction between templates and businesses logic is called data binding.
Types of Data Binding
1.	One-way Binding
2.	Two-Way binding
	One-Way Binding:  
			a) Component to View
o	Interpolation binding
o	Property Binding
o	Style Binding
o	Class Binding
o	Attribute Binding
			b) View to Component
o	Event Binding
 
Binding tuples can be grouped into three categories distinguished by the direction of data flow:
o	Source (Component)-to-view,
o	View-to-source (Component),
o	Two-way sequence: View-to-source (Component)-to-view
# Interpolation in Angular-16
	Interpolation is a technique that allows the user to bind a value to a UI element.
	Interpolation binds the data one-way. This means that when value of the field bound using interpolation changes, it is updated in the page as well. 	It cannot the value of the field.
	
	The format for defining interpolation in a template is: {{ propertyName }}
	Component ----------- {{ Value }} ----------> DOM
	# Property Binding
o	It is used to bind values of component/method properties to the HTML element.
o	Depending on the values, it will change the existing behaviour of the HTML element.
o	Syntax - [property]='expression'
o	In property binding, there is source and target. For this example, we can define it as [innerHTML]='firstName'. Here, innerHTML is a target that 	is a property of span tag and source is a component 	property i.e. firstName

	# Attribute Binding
	With attribute binding, can set the value of an attribute directly. The thing to note is that you must use the attribute binding only wen there is no element property to bind.
	Attribute binding is used to bind attribute of an element with the field of a component.
	<td [attr.colspan]="myColSpan" align="center">Employee Records </td>
	# Event Binding:
	When a user interacts with an application is the form of a keyboard movement, a mouse click, or a mouseover, it generates an event. These events need to be handle to perform some kind of action.
	This is where event binding comes into picture.
	Syntax
	Within parentheses on the left of the equal sign, we have the target event ("click" in this case) on the right side, we have the template statements such as component properties and methods.
	<button (click)="onClick()"> Click me </button>
	In this case, the onClick() method of the component class is called when the click event occurs.

# Two-Data binding: The most popular and widely used data binding mechanism is two-way binding in the angular framework. Basically two-way binding mainly used in the input field or any form element where user type of provide any value or change any control value in the one side, and on the other side, the same automatically update in to the controller variable and vice versa

# Pipes
Angular Pipes can be used to transform data to desired output.
Pipes takes in a data input and transforms data to a different output.
Using the Pipe operator (|), we can apply the Pipe's features to any of the property in our Angular project.
Pipes | in Angular are use to transform the data before displaying it in a browser. Angular provides a lot of build-in pipes to translate the data before displaying it into the browser and as we know, Angular lets us extend it feature, we can event create custom pipes in Angular.

# Parameterize Pipes
We can pass any number of parameters to the pipe using (:)
Like:
Data | pipename : parameter1: parameter2: parameter3....n
# chaining Pipes in Angular
 	Pipe   ↴
		✔️ Build-In Pipes ↴
				✔️ Parameterized
				✔️ Chaining
		✔️ Customer Pipes
	We can use multiple pipes with the same data at the same. This also referred to as chaining pipes 
•	data | pipe 1 | pipe 2| pipe |.... pipe n
•	data | pipe 1: parameter 1: parameter 2 : parameter 3 .... : parameter n | pipe 2 : parameter 1 parameter 2: parameter 3 .... : parameter n | pipe 3 : parameter 1 : parameter 2 : parameter 3 .... : parameter n

# Pipes with String in Angular 
	Uppercase 	Converts the string type data to upper case in the UI.
	 Lowercase 	Converts the string type data to lower case in the UI.
	Titlecase 	Converts the string data in which the first alphabet of each word is made capital and the string or array length.
	Slice: 	<string index> It works on string fields or Array. It slices the input for the index till the end of the string or array length.
	Slice: 	<string index>: <end index>	It works on string fields or array. it slices the input from the starting index to the end index. (excluding the end index) 

## Guidlines for Angular Developers
	Nevdr write the code for DOM manipulation in angular components, since Angular is designed in such a way to do this automatically based on changes to application data.
Example: If you update the value of the product price variable, the same thing will automatically update in the corresponding label on the page. In such a way, we create application logic to manipulate data but not to manipulate DOM directly. Therefor, we can execute unite testing at any time.
	Never write JavaScript code in Angular template, as the Angular templates that are HTML code will be converted into equivalent JavaScript code which provides DOM at run time. If we place JavaScript code in the Angular template, it will not compile properly with the Angular compiler.
	Never write business logic in components, because components are designed to store application data in the form of array or properties. it's also necessary to provide event handlers to the templates.
	Components are never intended to hold business logic, this business logic should be written in services and be invoked in the components. Business logic contains services to become independent of user interface and can be reusable across the application.

	Never using jQuery to manipulate DOM elements. In Angular we should not use jQuery to perform DOM manipulation such as getting, setting textbox values. But however, we can make use of limited jQuery code for some plugins such as drag & drop, model popup, etc.
# Date Pipes
There  are many date type pipes available in Angular. Following are some of the important ones.
o	shortDate - It converts the date to a short date.
o	longDate - It provides the long date for the date. Provides full month name then day and year.
o	fullDate - It provides the full date for the date. i.e. day, month date, year

# Percent Pipes
Percent pipe is used to display data in percent. i.e. 0.51 is displayed as 51 percent.
Syntax
number_expression | percent[:{minIntegerDigits}.{minFractionDigits}-{maxFractionDigits}
Where minIntegerDigits, minFractionDigits and maxFractionDigits have default values 1,0 and respectively.
# Currency Pipes
Currency Pipe displays data with currency format.
Syntax 
number_expression | currency [:currencyCode[:display[:{minIntegerDigits}.{minFractionDigits]-{maxFractionDigits}
{{ mynumber | currency: 'INR'}}
{{ mynumber | currency: 'INR':'code'}}
# json pipe in Angular
Json Pipe converts a value into JSON string
Syntax
expression | json
Example
{{ countries | json }}

# Customer Pipe
To create a pipe in Angular 16, you have to apply the  @ pipe decorator in class, which we can import from the core Angular library.
The @ Pipe decorator allows you to define the pipe name that you'll use within template expression.

Syntax
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
   name: '<pipe_name_here>'
})

export class Pipeclass implements PipeTransform{
	transform(parameters):<return_type_here>{}
}

Note: Transform() method will decide the input type, the number of arguments, and its types and output of our custom pipe.
# Routing in Angular
Routing is mechanism used by angular for navigation between page and displaying appropriated component/page on browser.
Angular framework is mainly focused and good for the SPA (Single Page Architecture). It loads a single full HTML page and dynamically load or updates the partial pages as per user request. And, that is achieved with the help of router. A set of partial page loading rule and URLs defined in router to render or load partial pages based on user request.
Angular routing helps navigation across the application from one view to another view. It also allows us to maintain the state, implement module, and load the modules based on the role of the user.
In component based architecture or Angular 16,  Angular looks into the routes array, match the path as per the route requested and loads the component relevant to the requested route as well as makes available the relevant data for that particular route.

Angular provides an easy way to create and work with components, in a single page application (SPA) it is essential to work with multiple views/screens, navigate and communicate between them. Angular provides router service to manage this in a very easy way.
An Angular application that users Angular Router only has one router service instance: It's a singleton. Wherever and wherever you inject the Router service in your application, you'll get access to the same Angular Router serves instance.
We access our application through one URL such as http://loclahost:4200 and our application is not aware of anu other URLs such as http://localhost:4200/login
Most web application need to support different URLs to navigate user to different pages in the application. That's where a router comes. 
**Angular Router** is an official Angular routing library, written and maintained by the Angular Core Team. It's a JavaScript router implementation that's designed to work with Angular and is packaged as @Anglular/router.

**First of all, Angular Router takes care of the duties of a JavaScript router:**
it activates all required Angular components to compose a page when a user navigates to a certain URL
it lets users navigate form one page to another without page reload
it updates the browser's history so the user can use the back and forward buttons when navigating back and forth between pages.
Angular Router allows us to:
	redirect a URL to another URL
	resolve data before a page is displayed
	run scripts when a page is activated or deactivated
	lazy load part of our application. 
# How Router Works
When a user navigates to a page, Angular Router performs the following steps in order:
Every time a link is clicked or the browser URL changes, Angular router makes sure your application reacts accordingly
To accomplish that, Angular router performs the following 7 steps in order:
Step 1: Parse the URL:
In step 1 of the routeing process, Angular router takes the browser URL and parses it as a URL tree. 
A URL tree is a data structure that will later help Angular router identify the router state in step 3
To parse the URL, Angular uses the following conventions:
o	 / - slashes divide URL segments
o	() - parenthesis specify		Secondary routes
o	: - a colon specifies 		name router outlet
o	; - a semicolon specifies a 		matrix parameter
o	? - a question mark separates the 	query string parameters
o	# - a hashtag specifies the 		fragment
o	// - a double slash separates multiple secondary routes
Step 2 Redirect 	
Before Angular routing uses the URL tree to create a router state, it checks to see if any redirect should applied. There are two kinds of redirect:
Local redirect: when redirectTo does not start with a slash. Replaces a single URL segment 
Example: { path: ‘one’, redirectTo: ‘two’ }
Absolute redirect: when redirectTo starts with a slash. Replaces the entire URL
Example: { path: ‘one’, rediredtTo: ‘/two’ }
Only onre redirect is applied! 

Step 3 – Identify the router state 
Angular router traverses the URS tree and matches the URL segments against the paths configured in the router configuration. 
If a URL segment matches the path of a router, the router’s child routers are matched against the remaining URL segments until all URL segments are matched.
If no complete match is found, the router backtracks to find a match in the next sibling route 
Step 4 – Gurd – run guards
At the moment, any user can navigate anywhere in the application anytime. That’s not always right thing to do.
Perhaps the user is not authorized to navigated to the target component.
Maybe the user must login (authenticate) first. 
Maybe you should fetch some data before you display the target component.
You might want to save pending changes before leaving a component.
You might ask the suer if it’s OK to discard pending changes rather than save them.
You can add guards to the route configuration to handle these scenarios.

Step 5 – Resolve – run resolvers
It resolves the required data for the router state.
Step 6 – Activate
It activates the Angular component to display the page.
Step 7 - Manage
Finally, when the new router state has been displayed to the screen, Angular router listens for URL changes and state changes.
It manages navigation and repeats the process when a new URL is requested.

# Router-outlet?
Router outlet is a dynamic component that the router uses to display views based on router navigations.
Router outlet is a Routing component. An Angular component with a RouterOutlet that displays views based on router navigations.
The role of <router-outliet> is to mark where the router displays a view. (This is the location where Angular will insert the component we want to route to on the view).

The <router-outlet> tells the router where to display routed views.
The RouterOutlet is one of the router directives that become available to the AppComponent because AppModule import AppRoutingModlue which exported RouterModule.
<nav [ngClass]=”menu”>
	<a routerLink=”/home” routerLinkActive=”active-link”>Home</a> | 
	<a routerLink=”/add-book” routerLinkActive=”active-link”>Add Book</a>| 
	<a routerLink=”/manage-book” routerLinkActive=”active-link”>Manage Book</a>
</nav>
<router-outlet></router-outlet>

#Router Link
With the help of the routerLink directive, we can link to routes of our application right from the html template. Just add the directive to an HTML-Element. When the user click on that element, angular navigates to the specified location.
The routerLink is the selector for the RouterLink directive that turns user click into router navigations. You can assign a string to the routrLink
The directive generates our link based on the router path.

Syntax

Template:
<h1>Angular Router</h1>
<div>
<a [routerLink]=”[‘/student’]”>Student</a>
<div>

<routet-outlet></routet-outlet>

For your application to work with server-side rendring, the element hosting the directive has the be a  link (a) element.
It is also possible, to navigate to a route from code. To do so, we need to the angular router.

Import {Router} form ‘@angular/router’;
Constructor(private router: Router){}

Once we have that router, navigation is quite simple. Just call the navigate function of Router. This function takes an array. The first entry of the array defines the string of the route, we want to navigate to. The second is optional and allows us to pass in a route parameter.

this.router.navigate([‘/student’, 738762]);

# Redirecting Router
A redirect route that translates the initial relative URL (“”) to the desired default path ( component-one) When application start, it navigates to the empty route by default. We can configure the router to redirect to a named route by default:

A router has no routes until you configure it.

Export const routes: Routes = [
   { path=’’, redirectTo: ‘component-one’, pathMathc: ‘full’},
   { path=’component-one’, component: ComponentOne },
   { path=’component-two, component: ComponentTwo },
]

	This route redirect a URL that fully matches the empty path to the route whose path is ‘component-one’
	A redirect route requires a pathMatch property to tell the router how to match a URL to the path  of a route. The router throws an error if you don’t.
	For the special case of an empty URL we also need to add the pathMatch: ‘full’ property so Angular knows it should be matching exactly the empty string and not partially the empty string.

#Wildcard route
Wildcard route to intercept invalid URLs and handle them gracefully.

A wildcard  router has a path consisting of two asterisks(**).
It matches every URL, the router will select this route if it can’t match a route earlier in the configuration. 
A wildcard route can navigate to a custome “404” Not found component or redirect to an existing route.

{ path: “**”,  component: PageNotFoundComponent } 

If the entire router configuration Is processed and there is no match, router navigation fails and and error is logged.
If you add a wildcard route as the first rout, no other routes would be reached and the wildcard route would always be matched. As a result, you should always add a wildcard route as the route in your router configuration.

## How to use Bootstrap in Angular?
Bootstrap is an open-source repository that provides a couple of native Angular widgets are build using Bootstrap 4 CSS. As you know Bootstrap is one of the most popular CSS frameworks which is used to build stylish and modern applications, which has HTML, CSS and JavaScript libraries. In order to use Bootstrap frameworks in the Angular app, earlier we would have had to use bootstrap CSS as well as it’s JavaScript files, but “ng-bootstrap” gives us the best approach to use without any JS file in our Angular applications.

No 3rd party libraries required
 Since “bootstrap” itself a module that encapsulates all of the Bootstrap functionality so there is no need to use any other 3rd party library into our Angular app. As a result, there is no dependency even on jQuery or on Bootstrap’s JavaScript library. Only dependencies are 
	Angular 4 and above
	Bootstrap 4.0.0 (CSS file only, Bootstrap.js and Bootstrap.min.js are not required)
Browser Support with “ng-bootstrap” module
It supports all of the browsers that has the same intersection of browsers supported by both Angular 4+ and Bootstrap 4.0.0 CSS only like,
	Chrome (latest)
	Firefox (latest)
	Edge (13+)
	IE (10+)
	iOS (7+)
	Android (5.0+)
	Safari (7+) and newer etc.

Installing bootstrap
Now we will see “How to install ng-bootstrap module to be used in angular apps?” so that we could use the bootstrap components provided by “ng-bootstrap”.
Since we have Angular 14 app creared by Angular CLI and using code editor as VS code, we will setup ng-bootstrap in the same application.

There are two way to use “ng-bootstrap” in an App,
First: Download Bootstrap CSS library from its official website and copy the bootstrap.min.css file and paste in into your Angular app (under src) folder and include it in styles array of Angular.json of app like:

Installing bootstrap
Second, install the Bootstrap module using npm command. Open VS code terminal window or you can use windows command prompt and type below command and install,
npm install bootstrap –save
To verify if the ng-bootstrap module is installed on our machine, go to package.json file of your app and check Bootstrap module.

Services In Angular

Services allow your code to share command functionality across the application. Create a single reusable service and inject it into the components that need it, which makes your code clean.

Services are an abstraction layer that handle an application’s business logic, which usually includes communicating with a backend and parsing/returning data or datasets.

An Angular services is simply a JavaScript function, including its related properties and methods which can perform a particular task or a group of tasks. Actually, services is a mechanism to use shared responsibilities within one or multiple components.

Services are a piece of code that are used to perform a specific task, a service can contain a value of function or combinations of both.

Services are injected into application using dependency injection mechanism. Services prevent us from writing the same code at multiple sections of our application. The best solution is to write services are injecting in application where we need it.

Service is a mechanism used to share the functionality b/w the component.

	An angular service is simple a function that allows us to access it’s defined properties and methods.
	It also helps keep our coding organized.
	You will most likely run into a scenario in which you need to use the same cod across multiple component.
	You will create a sing reusable data service and inject it into the component that need it.
	It easy to unit test component with a mack service.

Create a Service
We can create a custom service as per our requirement. For creating a service, we need to follow the below steps.
Step 1:  Create the Service File
Create a Service with the Angular-CLI
This is fairly easy, as it generates the scaffolding for you. In the command prompt, simply type;
Ng generate service myservicename
ng g s myservicename

Step 2: Import the Injectable Memer (it will be by default added when creating service through CLI cmd)
At the top of your new services file, and:
Import { Injectable } from ‘@angular/core’;

Step 3 : Add the Injectable Decorator (it will be by default added when creating service through CLI cmd ) 
In step 2, we imported the Injectable member from the Angular Core Library. Now we need to add the Injectable() decorator:
@Injectable()
Note:  As with all other Angular decorator, we proceed the name with an @symbol, and we don not add a semi-colon; at the end

Step 4: Export the Services Class
And finally, we create the class that contains the logic of our service:
export class ExampleService{
	// This is where our methods and properties go, for example;
     someMethod(){
	return ‘Hey!’;
      }
 }

Step 5: Import the Service to you component
Choose a component file and at the top, you must include the service member (line 2 below):
Import { Component } from ‘@angular/core’;
Import { ExampleService } form ‘./example.service’;

Step 6: Add it as a Provider
Now you must add it to the providers array in the Component decorator metadata if want to use this service on  component level (line 4 below):
@Component({
   Selector: ‘my-app’,
   Template: ‘<h1>{{title}}</h1>’,
   Providers: [ExampleService]
})

Setp: 7 Include it through dependency injection
In the constructor arguments of the component class, we include it through dependency injection:
Constructor (private_exampleService: ExampleService){}

Step 8 : Using the Service
Now we can access the service’s methods and properties by referencing the _exampleService.

For example: 
ngOnInit(){
  this.title =  this._exampleService.someMethod();
}

