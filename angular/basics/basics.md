# video #1:  How angular get loaded and started
1. What file gets loaded and served by the server to render the  page? 
   not the component html rather the index.html
2. Find another video with a better explanation.


# video #3: Components are importent
1.  Components are typically custom HTML elements, and each of these elements can instantiate only one component. 
2. A TypeScript class is used to create a component. This class is then decorated with the “@Component” decorator.
3. The decorator accepts a metadata object that gives information about the component.
4. A component must belong to the NgModule in order for it to be usable by another 5. component or application. 
5. Components control their runtime behavior by implementing Life-Cycle hooks. 



## Video 4: Creating a new component
* 
1. To create an Angular Component, Angular CLI is used. In the terminal, type in the command: 
  ng g c server

2. Angular creates a server folder and generates 4 server files inside that folder. Then it updates AppModule to import the component.

3. It is crucial for Angular to know which component is to be run next and its features. For that, some metadata is created.
3. @Component decorator accepts a metadata object that provides information about the component.
4. Selector
It is the CSS selector that identifies this component in a template. This corresponds to the HTML tag that is included in the parent component. You can create your own HTML tag. However, the same has to be included in the parent component. 

5. Template
It is an inline-defined template for the view. The template can be used to define some markup. The markup could typically include some headings or paragraphs that are displayed on the UI. 

6. TemplateUrl
It is the URL for the external file containing the template for the view. 

7. Styles
These are inline-defined styles to be applied to the component’s view 

8. styleUrls
List of URLs to stylesheets to be applied to the component’s view.  


   
## Video: Understanding the role of appModule and component declaration
#HOW TO MANUALLY REGISTER COMPONENTS: CLI AUTOMATICALLY DOES THIS!!!!
1. REGISTER component in app.module w/@ngModule: (anglular doesnt know component exists)
4. First: add to declaration Array
5. Add import at top of app.module that points to server.component.ts: import { ServerComponent} from './server/server.component';

## Video: Using Custom Components: explains the manual why. The CLI auto does this!

1. How do display component on page:
2. Place the component selector (fom server.component.ts) into the app.component.html
3. Place it between opening and closing tags. <app-server></app-server>

## Video: Creating Components with the CLI & Nesting Components
1. To create an Angular Component, Angular CLI is used. In the terminal, type in the command: 
2.  ng g c server

3. Angular creates a server folder and generates 4 server files inside that folder. Then it updates AppModule to import the component.

4. How to nest components w/in each other and use component selectors in other component templates.
     1. use cli to create a new servers component: it will auto create each folder and auto add to the modeles folder.
     1. In the servers.component.html AKA TEMPLATE: add the app.server component selector: <app.server></app.server>
     2. In the ROOT app.component.html update the selector to use the <app.servers></app.servers> selector




## Working with Component Templates

1. What does template file do: Renders UI in the browser.
2. You may use inline template or external template files to define html.
3. You MUST use at least one template file within servers.component.ts: either: template (internal): , or templateUrl(external);
4. for multiline html use template literal syntax


# Working with Component Styles

1. You may use inline styles or use the external styles file.
2. Within the component.ts. TO use internal styles just use the styles: key
3. To point to external file use stylesUrls key.
4. for inline styles use template strings w.in array and add multiple styles like normal.

# Fully Understanding Component Selectors

1. For selectors you may use attributes or classes instead of element selectors but best practice is to use an element selector

# Assignment component basics: problems
1. Create to new components in project: manually or using CLI
2. Output them beneath each other in the app comonent
3. Output a warning or success message in template
4. Style components



## String interpolation

1. Interpolation is used for one-way data binding in Angular. It embeds an expression into the HTML template. By default, expression should be surrounded by {{ and }}. This expression is also known as template expression.

2. {{ expression }}
Angular evaluates an expression surrounded by {{ and }} and then converts a result to a string and assigns it to an element or directive 

3. Example:
Add the below code in test.component.ts file as follows −

export class TestComponent implements OnInit { 
   appName = "My first app in Angular 8"; 
}
Move to test.component.html file and add the below code −

<h1>{{appName}}</h1>
Add the test component in your app.component.html file by replacing the existing content as follows −

<app-test></app-test>
Finally, start your application (if not done already) using the below command −

ng serve


## property binding
1. Property binding is used to bind the data from property of a component to DOM elements. It is denoted by [].

2. Add the below code in test.component.ts file.

export class TestComponent { 
   userName:string = "Peter"; 
}
3. Add the below changes in view test.component.html,
<input type="text" [value]="userName">
Here,
userName property is bind to an attribute of a DOM element <input> tag.

4.Finally, start your application (if not done already) using the below command −

ng serve

## Click Events

1. // app.component.html

<h1>{{ title }}</h1>
<app-test></app-test>

<button (click)="onClick()">Click Me!</button>

2. // app.component.ts 

export class AppComponent {
  title = 'first-app';
  
  onClick() {
    console.log('clicked');
  }

}

# Passing and using data w/ event binding
1. Use $event to grab data associated with eventbinding.
2. Scenerio: User inputs data into field. You want to display this data below the field. Use an (input)="method($event)" to grab needed data and pass into function to then add to variable which can be used via string interpolation in an element field.

# Two Way Data Binding
1. What is two way data binding? “Two-way binding gives components in your application a way to share data. Use two-way binding to listen for events and update values simultaneously between parent and child components“.

2. When we use two-way binding syntax we need to import NgModule and FormsModule in app.module.ts,



3. Example: user types the name of a book in the input field and it is later added as interpoloation to an element field

// input-component.html
<h2>Add a new title</h2>
<div>
  <input type="text" placeholder="Write a title" [(ngModel)]="bookTitle">
  <button (click)="onAddBook()">Add Title</button>
</div>

onAddTitle() {
    console.log('book in ChildComponent:', this.bookTitle);
  }

## What are directives?

1. instructions in the DOM
2. Components are directives with a template.
3. Directives typically use attribute style. But could also use element, or css selector style
## built in directives:
## structural directives
1. ngIf : uses * which means its changes structure of dom(adds or doesnt add element)
          ngIf uses boolean
2. Use else with ngIf: 
## Attribute directives: change the element they were placed on
1. ngStyles allow you to dynamically update the styles

