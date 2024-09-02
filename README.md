<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Angular 16 Overview</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background-color: #f9f9f9;
            color: #333;
        }
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1, h2, h3, h4, h5, h6 {
            color: #333;
            margin-top: 1.2em;
        }
        p {
            margin: 10px 0;
        }
        ul {
            padding-left: 20px;
            margin: 10px 0;
        }
        code {
            background-color: #f4f4f4;
            padding: 2px 4px;
            border-radius: 4px;
            font-family: monospace;
        }
        pre {
            background-color: #f4f4f4;
            padding: 10px;
            border-radius: 4px;
            overflow-x: auto;
        }
        .highlight {
            background-color: #e2f0ff;
            padding: 5px;
            border-left: 3px solid #007acc;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Angular 16 Overview</h1>

        <h2>What you should already know</h2>
        <ul>
            <li>HTML and Document Object Model (DOM)</li>
            <li>CSS (optional)</li>
            <li>JavaScript</li>
            <li>TypeScript</li>
            <li>Basic concepts of Object-Oriented Programming (OOP)</li>
        </ul>

        <h2>Why Developers Choose Angular</h2>
        <ul>
            <li>Separation of DOM manipulation logic from application logic</li>
            <li>Separation of HTML logic from application logic</li>
            <li>Easy code maintenance</li>
            <li>Develop single-page applications more easily</li>
            <li>Make the code unit-testable</li>
            <li>Popular companies using Angular: YouTube, Google Cloud, Nike, HBO, Sony, Crunchbase</li>
        </ul>

        <h2>Main Building Blocks of an Angular Application</h2>
        <ul>
            <li>Modules</li>
            <li>Components</li>
            <li>Templates</li>
            <li>Metadata</li>
            <li>Data Binding</li>
            <li>Directives</li>
            <li>Services</li>
            <li>Dependency Injection</li>
        </ul>

        <h3>Modules</h3>
        <p>Every Angular application must have at least one module. If the Angular application contains only one module, it is referred to as the root module. Every Angular application has one root module and may have many feature modules. An Angular module is a class decorated with <code>@NgModule</code>. <code>NgModule</code> takes a single metadata object, and its properties describe the module.</p>
        <ul>
            <li><strong>Exports</strong> - Subset of declarations that can be used in component templates of other modules.</li>
            <li><strong>Imports</strong> - Import other modules.</li>
            <li><strong>Providers</strong> - Service creators. They can be accessible in all parts of the application.</li>
            <li><strong>Bootstrap</strong> - The root module sets the bootstrap property, used to host all other views.</li>
            <li><strong>Declarations</strong> - Declare view classes that belong to the current module. There are three types of view classes supported by Angular: components, directives, and pipes.</li>
        </ul>

        <h3>Components</h3>
        <p>A component is a class with a template that deals with the view of the application and contains the core logic of the page. In Angular, the component class interacts with the view through methods and properties of the API.</p>
        <pre><code>import { Component } from '@angular/core';
@Component({
  selector: 'test-app',
  template: '<h1>This is my First Angular 2 Application</h1>'+
            '<br/>'+
            '<input #txtName type="text" (keyup)="0">'+
            '<br/>'+
            '<p>You have Enter: {{txtName.value}}</p>'
})
export class AppComponent { }</code></pre>

        <h3>Template</h3>
        <p>The template is the component view that tells Angular how to display the component. It looks like normal HTML.</p>

        <h3>Service</h3>
        <p>A service in Angular is a function or object used to share data and behavior across the application. Services are a way to encapsulate business logic and data interaction in Angular applications.</p>

        <h3>Directive</h3>
        <p>Directives are used to extend the power of HTML attributes and change the appearance or behavior of a DOM element. Angular has three types of directives:</p>
        <ul>
            <li>Component Directives</li>
            <li>Structural Directives</li>
            <li>Attribute Directives</li>
        </ul>

        <h3>Dependency Injection</h3>
        <p>Dependency Injection is a software design pattern in which objects are passed as dependencies. It helps remove hardcoded dependencies and makes them configurable.</p>

        <h2>Basic Architecture of an Angular Application</h2>
        <p>The basic architecture of an Angular application includes:</p>
        <ul>
            <li>Index.html</li>
            <li>main.ts</li>
            <li>app.module.ts</li>
            <li>app.component.ts</li>
            <li>app.component.html</li>
        </ul>

        <h2>Angular Environment Setup</h2>
        <p>To set up a development environment for Angular, you need:</p>
        <ul>
            <li>IDE for writing code (e.g., Visual Studio Code)</li>
            <li>Node.js</li>
            <li>NPM (Node Package Manager)</li>
            <li>Angular CLI</li>
        </ul>

        <h3>IDE for Writing Code</h3>
        <p>Various editors can be used for Angular development. In this course, we use Visual Studio Code, a free editor from Microsoft.</p>

        <h3>Angular CLI</h3>
        <p>To install Angular CLI globally on your system, type <code>npm install -g @angular/cli</code>.</p>

        <h3>Common Commands</h3>
        <p>Some common commands for working with Angular CLI:</p>
        <ul>
            <li>Verify if npm is installed: <code>npm -v</code></li>
            <li>Verify the installed version of Node.js: <code>node -v</code></li>
            <li>Install Angular CLI globally: <code>npm install -g @angular/cli</code></li>
            <li>Check the installed Angular CLI version: <code>ng v</code></li>
        </ul>

        <h2>Why Does Angular 16 Need Node.js?</h2>
        <p>Node.js is a server-side platform built on Google Chrome's JavaScript Engine (V8 Engine). It provides a runtime environment for developing server-side and networking applications. Angular 16 requires Node.js for several reasons:</p>
        <ul>
            <li>Node.js allows you to spin up a lightweight web server to host your application locally.</li>
            <li>NPM (Node Package Manager) comes with Node.js by default, allowing you to manage dependencies.</li>
            <li>Angular CLI (ng CLI) is provided by NPM, making it easy to scaffold applications.</li>
        </ul>

        <h2>What is Angular CLI?</h2>
        <p>The Angular CLI is a command-line interface tool used to initialize, develop, scaffold, and maintain Angular applications directly from a command shell. To install Angular CLI globally, use the command:</p>
        <pre><code>npm install -g @angular/cli</code></pre>

        <h2>Package.json and Package-lock.json Files</h2>
        <p>The <code>package.json</code> file is mandatory for every npm project. It contains basic information about the project, commands, dependencies, and devDependencies. The <code>package-lock.json</code> file records the same versions of each installed package, ensuring that future installs build an identical dependency tree.</p>

        <h2>Booting Process of an Angular Application</h2>
        <p>The workflow of an Angular application typically follows this sequence:</p>
        <ul>
            <li><code>Index.html</code></li>
            <li><code>main.ts</code></li>
            <li><code>app.module.ts</code></li>
            <li><code>app.component.ts</code></li>
            <li><code>app.component.html</code></li>
        </ul>

        <h2>Angular Decorators</h2>
        <p>Decorators are a feature of TypeScript implemented as functions. In Angular, decorators are used to define modules, components, services, and more.</p>
        <ul>
            <li><code>@NgModule()</code> - Defines modules.</li>
            <li><code>@Component()</code> - Defines components.</li>
            <li><code>@Injectable()</code> - Defines services.</li>
            <li><code>@Input()</code> and <code>@Output()</code> - Define properties that send and receive data from the DOM.</li>
        </ul>

        <h2>Common Angular Decorators</h2>
        <ul>
            <li><code>@HostListener()</code> - A function decorator that accepts an event name as an argument.</li>
        </ul>

        <h2>Basic Architecture of an Angular Application</h2>
        <p>An Angular application consists of a tree of Angular components, with a root component at the top. When bootstrapped, Angular renders the root component, which in turn renders its child components.</p>

        <h2>Selector in Angular</h2>
        <p>The <code>selector</code> attribute in Angular allows you to define how Angular identifies and inserts a component instance in the DOM. The selector is specified as a string value in the component's metadata.</p>

        <h2>Template and TemplateURL</h2>
        <p>In Angular, templates can be defined inline or in external files using the <code>template</code> and <code>templateURL</code> properties, respectively.</p>

        <h2>Style and StyleURL</h2>
        <p>Angular components can have inline styles specified directly in the component's metadata using the <code>style</code> property or external styles defined in separate files using the <code>styleUrls</code> property.</p>

        <h2>Encapsulation in Angular</h2>
        <p>Angular provides three types of view encapsulation to emulate the shadow DOM and encapsulate styles:</p>
        <ul>
            <li><strong>Emulated (default)</strong> - No shadow DOM, styles are encapsulated within the component.</li>
            <li><strong>Native</strong> - Shadow DOM, styles are encapsulated within the component.</li>
            <li><strong>None</strong> - No shadow DOM, styles are not encapsulated.</li>
        </ul>

        <h2>Provider Property in Angular</h2>
        <p>The <code>providers</code> metadata is used to configure providers at the module or component level, allowing dependency injection in Angular applications.</p>

        <h2>Parent to Child Communication with Input Property</h2>
        <p>The <code>@Input</code> property allows a parent component to pass data to a child component. This is one-way communication from parent to child.</p>

        <h2>Child to Parent Communication with Output Property</h2>
        <p>The <code>@Output</code> property allows a child component to send data to a parent component through custom events. This is one-way communication from child to parent.</p>

        <h2>Directives in Angular 16</h2>
        <p>Directives in Angular are JavaScript classes declared as <code>@Directive</code>. There are three types of directives in Angular:</p>
        <ul>
            <li>Component Directives</li>
            <li>Structural Directives</li>
            <li>Attribute Directives</li>
        </ul>

        <h3>Component Directives</h3>
        <p>Component Directives are special directives that include templates and define components in Angular applications.</p>

        <h3>Structural Directives</h3>
        <p>Structural Directives manipulate the DOM by adding, removing, or changing elements. Common structural directives include <code>*ngIf</code> and <code>*ngFor</code>.</p>

        <h3>Attribute Directives</h3>
        <p>Attribute Directives are used to modify the appearance or behavior of DOM elements. Examples include <code>ngClass</code> and <code>ngStyle</code>.</p>

        <h2>Angular Data Binding</h2>
        <p>Data binding in Angular refers to the interaction between templates and business logic. There are two types of data binding:</p>
        <ul>
            <li><strong>One-Way Binding</strong> - Data flows in one direction from component to view or view to component.</li>
            <li><strong>Two-Way Binding</strong> - Data flows in both directions, commonly used in forms.</li>
        </ul>

        <h3>Interpolation in Angular 16</h3>
        <p>Interpolation allows binding a value to a UI element using the syntax <code>{{ propertyName }}</code>.</p>

        <h3>Property Binding</h3>
        <p>Property binding binds component properties to HTML element properties. Syntax: <code>[property]='expression'</code>.</p>

        <h3>Attribute Binding</h3>
        <p>Attribute binding sets the value of an attribute directly when there is no element property to bind.</p>

        <h3>Event Binding</h3>
        <p>Event binding handles user interactions such as clicks or keyboard events. Syntax: <code>(event)="handler()"</code>.</p>

        <h2>Pipes in Angular 16</h2>
        <p>Angular Pipes transform data before displaying it in the browser. Pipes can be parameterized and chained together for more complex transformations.</p>

        <h3>Common Pipes in Angular</h3>
        <ul>
            <li><strong>Uppercase</strong> - Converts string data to uppercase.</li>
            <li><strong>Lowercase</strong> - Converts string data to lowercase.</li>
            <li><strong>Titlecase</strong> - Converts the first letter of each word to uppercase.</li>
            <li><strong>Slice</strong> - Slices a string or array.</li>
        </ul>

        <h2>Guidelines for Angular Developers</h2>
        <div class="highlight">
            <ul>
                <li>Avoid writing DOM manipulation code in Angular components; Angular handles it automatically.</li>
                <li>Avoid writing JavaScript code in Angular templates; use Angular's built-in features instead.</li>
                <li>Avoid writing business logic in components; use services instead.</li>
                <li>Avoid using jQuery for DOM manipulation; rely on Angular's capabilities.</li>
            </ul>
        </div>

        <h3>Date Pipes</h3>
        <ul>
            <li><strong>shortDate</strong> - Converts the date to a short format.</li>
            <li><strong>longDate</strong> - Converts the date to a long format.</li>
            <li><strong>fullDate</strong> - Converts the date to a full format.</li>
        </ul>

        <h3>Percent Pipes</h3>
        <p>Percent pipes display data in percentage format. Example: 0.51 is displayed as 51%.</p>

        <h3>Currency Pipes</h3>
        <p>Currency pipes display data in currency format. Example: <code>{{ mynumber | currency: 'INR' }}</code>.</p>

        <h3>JSON Pipes</h3>
        <p>JSON Pipes convert a value into a JSON string. Example: <code>{{ countries | json }}</code>.</p>

        <h3>Custom Pipes</h3>
        <p>To create a custom pipe in Angular 16, apply the <code>@Pipe</code> decorator to a class.</p>
        <pre><code>import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
    name: 'myCustomPipe'
})
export class MyCustomPipe implements PipeTransform {
    transform(value: any, ...args: any[]): any {
        // Custom transformation logic here
        return transformedValue;
    }
}</code></pre>

        <h2>Routing in Angular 16</h2>
        <p>Routing in Angular allows navigation between different views or pages. It uses the <code>@angular/router</code> package to manage the navigation process.</p>

        <h3>Router-outlet</h3>
        <p>The <code>&lt;router-outlet&gt;</code> is a dynamic component that displays views based on router navigations. It marks where the router displays the component for the current route.</p>

        <h3>Router Link</h3>
        <p>The <code>routerLink</code> directive is used to navigate between routes within the application. Example:</p>
        <pre><code>&lt;a [routerLink]="['/student']"&gt;Student&lt;/a&gt;</code></pre>

        <h3>Redirecting Router</h3>
        <p>Angular allows configuring the router to redirect from one route to another. Example:</p>
        <pre><code>{ path: '', redirectTo: 'component-one', pathMatch: 'full' }</code></pre>

        <h3>Wildcard Route</h3>
        <p>The wildcard route <code>**</code> is used to match any invalid URL and navigate to a "Not Found" page.</p>

        <h2>How to Use Bootstrap in Angular?</h2>
        <p>Bootstrap is a popular CSS framework. It can be used in Angular applications by either downloading the Bootstrap CSS file or installing it via npm:</p>
        <pre><code>npm install bootstrap --save</code></pre>

        <h2>Services in Angular</h2>
        <p>Services in Angular allow you to share common functionality across multiple components. A service is a JavaScript function or class that contains logic to perform a specific task or group of tasks.</p>

        <h3>Creating a Service</h3>
        <p>To create a service in Angular, follow these steps:</p>
        <ol>
            <li>Create a service file using Angular CLI: <code>ng generate service myServiceName</code>.</li>
            <li>Import the <code>Injectable</code> member: <code>import { Injectable } from '@angular/core';</code>.</li>
            <li>Add the <code>@Injectable()</code> decorator to the service class.</li>
            <li>Export the service class and define its methods and properties.</li>
            <li>Import the service into the component and add it to the providers array in the component's metadata.</li>
            <li>Include the service through dependency injection in the component's constructor.</li>
        </ol>
        <pre><code>import { Injectable } from '@angular/core';

@Injectable()
export class ExampleService {
    someMethod() {
        return 'Hey!';
    }
}</code></pre>

        <h3>Using the Service</h3>
        <p>Once the service is created, you can use its methods and properties within your component:</p>
        <pre><code>import { Component } from '@angular/core';
import { ExampleService } from './example.service';

@Component({
  selector: 'my-app',
  template: '&lt;h1&gt;{{ title }}&lt;/h1&gt;',
  providers: [ExampleService]
})
export class AppComponent {
  title: string;

  constructor(private exampleService: ExampleService) {}

  ngOnInit() {
    this.title = this.exampleService.someMethod();
  }
}</code></pre>
    </div>
</body>
</html>
  
