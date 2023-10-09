# video #1:  What the hell is Angular?

What is angular? Anglular is a framework that allows you to make SPA's. THe page does not refresh every change is redered in browser.


# Video #2: Angular One vs Angular 2

Angular One aka Angular Js was not future proof and was rewritten in 2016 for Angular 2. Angular One is deprecated and Angular two is not used either. Angular updates/new version occur every six months. Angular 2 and older versions just refered to as Angular

## Video #3: Angular setup and first app
* IF ALL THE BELOW STEPS ARE DONE START AT STEP 4:
1. Download Anglular CLI: In terminal(zsh) run: sudo npm install -g @angular/cli#latest
2. You will get errors doing install: look for message @ bottom @anglular/cli....version
3. . Make sure have node LTS installed not latest version.
4. Create Project ClI: mkdir (create folder)... Cd into folder..
5. Once in folder run: ng new  my-first-app --no-no-strict --skip git(name project anything u like)
6. for the message: would you like angular routing: select No
7.  Next, select CSS
8. once downloaded: cd into folder!
9. run: ng serve (to enter development server)
server runs on: localhost:4200 by defaultnpm insta
6.  double-check that you have npm version 6 installed .
3.  Since npm v7 can cause issues, you should ensure that you use v6.  run npm install -g npm@6 to ensure that you are using that version (on macOS, you might need to add sudo in front of that command).
4. Updating NodeJS:
7. Go to nodejs.org and download the latest version - uninstall (all) installed versions on your machine first.
8. Updating npm:
9. Run [sudo] npm install -g npm (sudo is only required on Mac/ Linux)
10. Updating the CLI
[sudo] npm uninstall -g angular-cli @angular/cli 
11. npm cache clean 
[sudo] npm install -g @angular/cli 

12. Here are some common issues & solutions:
Creation of a new project takes forever (longer than 3 minutes)
That happens on Windows from time to time => Try running the command line as administrator
You get an EADDR error (Address already in use)
You might already have another ng serve process running - make sure to quit that or use ng serve --port ANOTHERPORT  to serve your project on a new port
My changes are not reflected in the browser (App is not compiling)
Check if the window running ng serve displays an error. If that's not the case, make sure you're using the latest CLI version and try restarting your CLI
 


## Video #4 Editing the First App:
1. Keep localhost:4200 running (run it by typing ng serve in the terminal).
2. stop server when done by pressing: Ctrl + C
3. Angular uses data binding which is used to output dynamic content in our html.


## Creating a new component
* FIRST NAVIGATE TO PROJECT FOLDER: 
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

4. How to nest components w/in each other and use component selectors in other component templates.
     1. use cli to create a new servers component: it will auto create each folder and auto add to the modeles folder.
     1. In the servers.component.html AKA TEMPLATE: add the app.server component selector: <app.server></app.server>
     2. In the ROOT app.component.html update the selector to use the <app.servers></app.servers> selector

