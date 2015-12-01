#### cookie vs session
- The data of cookie is stored in local browser, thus it is not safe.
- The data of session is stored in the server for some time.

#### What is MVC?
- Model: managing data; 
- Controller: application logic; 
- View: presenting data

#### GET vs POST?
- GET: retrieve representations of resources; no side effects; no data in request body. 
- POST: upload data from the browser to server; returns information from the server; side effects are likely; data contained in the request body.

#### AngularJS
- client-side templating. templates, which are HTML documents defining the UI, are loaded from server; once in the browser, Angular merges template with data, defining a vew.

- template data binding. Use $scope to expose model data to view. Views dynamically load template fragment via routes

#### AngularJS vs ExpressJS
#### Client-side rendering vs Server-side rendering